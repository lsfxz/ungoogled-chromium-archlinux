# Derived from PKGBUILD for Inox
# Original Inox PKGBUILD authors:
# Maintainer: Michael Egger <gcarq@archlinux.info>
# Contributor: Evangelos Foutras <evangelos@foutrelis.com>
# Contributor: Pierre Schmitz <pierre@archlinux.de>
# Contributor: Jan "heftig" Steffens <jan.steffens@gmail.com>
# Contributor: Daniel J Griffiths <ghost1227@archlinux.us>

pkgname=inox
_pkgname=ungoogled-chromium
# Commit or tag for the upstream ungoogled-chromium repo
_ungoogled_version='77.0.3865.90-1'
_ungoogled_archlinux_version=23b8ab6
_chromium_version=$(curl -sL https://raw.githubusercontent.com/Eloston/ungoogled-chromium/${_ungoogled_version}/chromium_version.txt)
_ungoogled_revision=$(curl -sL https://raw.githubusercontent.com/Eloston/ungoogled-chromium/${_ungoogled_version}/revision.txt)
pkgver=${_chromium_version}
_ungoogled_archlinux_pkgrel=0
pkgrel=$((_ungoogled_revision + _ungoogled_archlinux_pkgrel))
_launcher_ver=6
pkgdesc="A lightweight approach to removing Google web service dependency - inox branded"
arch=('x86_64')
url="https://github.com/ungoogled-software/ungoogled-chromium-archlinux"
license=('BSD')
depends=('gtk3' 'nss' 'alsa-lib' 'xdg-utils' 'libxss' 'libcups' 'libgcrypt'
         'ttf-font' 'systemd' 'dbus' 'libpulse' 'pciutils' 'json-glib' 'libva'
         'desktop-file-utils' 'hicolor-icon-theme' 'jsoncpp' 'openjpeg2')
makedepends=('python' 'python2' 'gperf' 'yasm' 'mesa' 'ninja' 'git'
             'clang' 'lld' 'gn' 'llvm' 'quilt')
optdepends=('pepper-flash: support for Flash content'
            'kdialog: needed for file dialogs in KDE'
            'gnome-keyring: for storing passwords in GNOME keyring'
            'kwallet: for storing passwords in KWallet'
            'libva-intel-driver: for hardware video acceleration with Intel GPUs'
            'libva-mesa-driver: for hardware video acceleration with AMD/ATI GPUs'
            'libva-vdpau-driver: for hardware video acceleration with NVIDIA GPUs')
provides=('inox')
conflicts=('inox')
source=(https://commondatastorage.googleapis.com/chromium-browser-official/chromium-${_chromium_version}.tar.xz
        chromium-launcher-$_launcher_ver.tar.gz::https://github.com/foutrelis/chromium-launcher/archive/v$_launcher_ver.tar.gz
        "git+https://github.com/lsfxz/ungoogled-chromium-archlinux.git#commit=${_ungoogled_archlinux_version}"
        "https://raw.githubusercontent.com/GrapheneOS/Vanadium/609ac77401cdcf085051b894420856463eb52e20/0010-disable-seed-based-field-trials.patch"
        "git+https://github.com/Eloston/ungoogled-chromium#tag=${_ungoogled_version}")
sha256sums=('eb952ff241e719cbdcc2aae1832ecc1dd2263736ab38ee1dbf88ac9120119789'
            '04917e3cd4307d8e31bfb0027a5dce6d086edb10ff8a716024fbb8bb0c7dccf1'
            'SKIP'
            '413c4bffa2acc3b3d8c05bb38a8ab8c42be19e3e2fd9bd10b3739b7647ec7cb1'
            'SKIP')

# Possible replacements are listed in build/linux/unbundle/replace_gn_files.py
# Keys are the names in the above script; values are the dependencies in Arch
declare -gA _system_libs=(
  [ffmpeg]=ffmpeg
  [flac]=flac
  [fontconfig]=fontconfig
  [freetype]=freetype2
  [harfbuzz-ng]=harfbuzz
  [icu]=icu
  [libdrm]=
  [libevent]=libevent
  [libjpeg]=libjpeg
  #[libpng]=libpng            # https://crbug.com/752403#c10
  [libvpx]=libvpx
  [libwebp]=libwebp
  [libxml]=libxml2
  [libxslt]=libxslt
  [opus]=opus
  [re2]=re2
  [snappy]=snappy
  [yasm]=
  [zlib]=minizip
)
_unwanted_bundled_libs=(
  ${!_system_libs[@]}
  ${_system_libs[libjpeg]+libjpeg_turbo}
)
depends+=(${_system_libs[@]})

prepare() {
  _ungoogled_archlinux_repo="$srcdir/ungoogled-chromium-archlinux"
  _ungoogled_repo="$srcdir/$_pkgname"
  _utils="${_ungoogled_repo}/utils"

  cd "$srcdir/chromium-${_chromium_version}"

  msg2 'Pruning binaries'
  python "$_utils/prune_binaries.py" ./ "$_ungoogled_repo/pruning.list"
  msg2 'Applying patches'
  python "$_utils/patches.py" apply ./ "$_ungoogled_repo/patches" "$_ungoogled_archlinux_repo/patches"
  patch -Np1 -i ${_ungoogled_archlinux_repo}/other/0012-branding.patch
  patch -Np1 -i ../0010-disable-seed-based-field-trials.patch
  msg2 'Applying domain substitution'
  python "$_utils/domain_substitution.py" apply -r "$_ungoogled_repo/domain_regex.list" -f "$_ungoogled_repo/domain_substitution.list" -c domainsubcache.tar.gz ./

 # https://crbug.com/893950
  sed -i -e 's/\<xmlMalloc\>/malloc/' -e 's/\<xmlFree\>/free/' \
    third_party/blink/renderer/core/xml/*.cc \
    third_party/blink/renderer/core/xml/parser/xml_document_parser.cc \
    third_party/libxml/chromium/libxml_utils.cc

  # Force script incompatible with Python 3 to use /usr/bin/python2
  sed -i '1s|python$|&2|' third_party/dom_distiller_js/protoc_plugins/*.py

  # Remove bundled libraries for which we will use the system copies; this
  # *should* do what the remove_bundled_libraries.py script does, with the
  # added benefit of not having to list all the remaining libraries
  local _lib
  for _lib in ${_unwanted_bundled_libs[@]}; do
    find -type f -path "*third_party/$_lib/*" \
      \! -path "*third_party/$_lib/chromium/*" \
      \! -path "*third_party/$_lib/google/*" \
      \! -path './base/third_party/icu/*' \
      \! -path './third_party/crashpad/crashpad/third_party/zlib/zlib_crashpad.h' \
      \! -path './third_party/pdfium/third_party/freetype/include/pstables.h' \
      \! -path './third_party/yasm/run_yasm.py' \
      \! -regex '.*\.\(gn\|gni\|isolate\)' \
      -delete
  done

  python2 build/linux/unbundle/replace_gn_files.py \
    --system-libraries "${!_system_libs[@]}"

  msg2 'Applying Chromium launcher patches'
  cd "$srcdir/chromium-launcher-$_launcher_ver"
  patch -Np1 -i ${_ungoogled_archlinux_repo}/other/0020-launcher-branding.patch
}

build() {
  _ungoogled_archlinux_repo="$srcdir/ungoogled-chromium-archlinux"
  _ungoogled_repo="$srcdir/$_pkgname"

  make -C chromium-launcher-$_launcher_ver

  cd "$srcdir/chromium-${_chromium_version}"

  if check_buildoption ccache y; then
    # Avoid falling back to preprocessor mode when sources contain time macros
    export CCACHE_SLOPPINESS=time_macros
  fi

  export CC=clang
  export CXX=clang++
  export AR=llvm-ar
  export NM=llvm-nm

  mkdir -p out/Default

  # Assemble GN flags
  cp "$_ungoogled_repo/flags.gn" "out/Default/args.gn"
  printf '\n' >> "out/Default/args.gn"
  cat "$_ungoogled_archlinux_repo/flags.archlinux.gn" >> "out/Default/args.gn"

  # Facilitate deterministic builds (taken from build/config/compiler/BUILD.gn)
  CFLAGS+='   -Wno-builtin-macro-redefined'
  CXXFLAGS+=' -Wno-builtin-macro-redefined'
  CPPFLAGS+=' -D__DATE__=  -D__TIME__=  -D__TIMESTAMP__='

  msg2 'Configuring Chromium'
  gn gen out/Default --script-executable=/usr/bin/python2 --fail-on-unused-args
  msg2 'Building Chromium'
  ninja -C out/Default chrome chrome_sandbox chromedriver
}

package() {
  _ungoogled_archlinux_repo="$srcdir/ungoogled-chromium-archlinux"

  cd chromium-launcher-$_launcher_ver
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -Dm644 LICENSE \
    "$pkgdir/usr/share/licenses/$pkgname/LICENSE.launcher"

  cd "$srcdir/chromium-${_chromium_version}"

  install -D out/Default/chrome "$pkgdir/usr/lib/$pkgname/$pkgname"
  install -Dm4755 out/Default/chrome_sandbox "$pkgdir/usr/lib/$pkgname/chrome-sandbox"
  install -D out/Default/chromedriver "$pkgdir/usr/lib/$pkgname/inoxdriver"
  ln -s /usr/lib/$pkgname/inoxdriver "$pkgdir/usr/bin/inoxdriver"
  install -Dm644 chrome/installer/linux/common/desktop.template \
    "$pkgdir/usr/share/applications/$pkgname.desktop"
  install -Dm644 chrome/app/resources/manpage.1.in \
    "$pkgdir/usr/share/man/man1/$pkgname.1"
  sed -i \
    -e "s/@@MENUNAME@@/Inox/g" \
    -e "s/@@PACKAGE@@/$pkgname/g" \
    -e "s/@@USR_BIN_SYMLINK_NAME@@/$pkgname/g" \
    "$pkgdir/usr/share/applications/$pkgname.desktop" \
    "$pkgdir/usr/share/man/man1/$pkgname.1"

  cp \
    out/Default/{chrome_{100,200}_percent,resources}.pak \
    out/Default/*.bin \
    "$pkgdir/usr/lib/$pkgname/"
  install -Dm644 -t "$pkgdir/usr/lib/$pkgname/locales" out/Default/locales/*.pak

  if [[ -z ${_system_libs[icu]+set} ]]; then
    cp out/Default/icudtl.dat "$pkgdir/usr/lib/$pkgname/"
  fi

  for size in 16 22 24 32 48 64 128 256; do
    install -Dm644 "${_ungoogled_archlinux_repo}/other/product_logo_$size.png" \
      "$pkgdir/usr/share/icons/hicolor/${size}x${size}/apps/$pkgname.png"
  done

  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

# vim:set ts=2 sw=2 et:
