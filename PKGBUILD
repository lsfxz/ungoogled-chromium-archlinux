# Derived from PKGBUILD for Inox
# Original Inox PKGBUILD authors:
# Maintainer: Michael Egger <gcarq@archlinux.info>
# Contributor: Evangelos Foutras <evangelos@foutrelis.com>
# Contributor: Pierre Schmitz <pierre@archlinux.de>
# Contributor: Jan "heftig" Steffens <jan.steffens@gmail.com>
# Contributor: Daniel J Griffiths <ghost1227@archlinux.us>

pkgname=inox
_pkgname=ungoogled-chromium
pkgver=78.0.3904.87
pkgrel=1
_launcher_ver=6
_ungoogled_commit=497a6e7d0e3d116f987d3763aa5550d3a7b8c7d5
pkgdesc="A lightweight approach to removing Google web service dependency - inox branded"
arch=('x86_64')
url="https://github.com/ungoogled-software/ungoogled-chromium-archlinux"
license=('BSD')
depends=('gtk3' 'nss' 'alsa-lib' 'xdg-utils' 'libxss' 'libcups' 'libgcrypt'
         'ttf-font' 'systemd' 'dbus' 'libpulse' 'pciutils' 'json-glib'
         'desktop-file-utils' 'hicolor-icon-theme')
makedepends=('python' 'python2' 'gperf' 'yasm' 'mesa' 'ninja' 'nodejs' 'git'
             'pipewire' 'clang' 'lld' 'gn' 'java-runtime-headless')
optdepends=('pepper-flash: support for Flash content'
            'kdialog: needed for file dialogs in KDE'
            'gnome-keyring: for storing passwords in GNOME keyring'
            'kwallet: for storing passwords in KWallet'
            'libva-intel-driver: for hardware video acceleration with Intel GPUs'
            'libva-mesa-driver: for hardware video acceleration with AMD/ATI GPUs'
            'libva-vdpau-driver: for hardware video acceleration with NVIDIA GPUs')
provides=('inox')
conflicts=('inox')
_raw_github=https://raw.githubusercontent.com/lsfxz/ungoogled-chromium-archlinux/inox
source=(https://commondatastorage.googleapis.com/chromium-browser-official/chromium-${pkgver}.tar.xz
        chromium-launcher-$_launcher_ver.tar.gz::https://github.com/foutrelis/chromium-launcher/archive/v$_launcher_ver.tar.gz
        "ungoogled-chromium::git+https://github.com/Eloston/ungoogled-chromium.git#commit=${_ungoogled_commit}"
        "https://raw.githubusercontent.com/GrapheneOS/Vanadium/10/0009-disable-seed-based-field-trials.patch"
        https://patch-diff.githubusercontent.com/raw/Eloston/ungoogled-chromium/pull/848.patch
        flags.archlinux.gn
        inox-drirc-disable-10bpc-color-configs.conf
        "${_raw_github}/inox/product_logo_16.png"
        "${_raw_github}/inox/product_logo_22.png"
        "${_raw_github}/inox/product_logo_24.png"
        "${_raw_github}/inox/product_logo_32.png"
        "${_raw_github}/inox/product_logo_48.png"
        "${_raw_github}/inox/product_logo_64.png"
        "${_raw_github}/inox/product_logo_128.png"
        "${_raw_github}/inox/product_logo_256.png"
        "${_raw_github}/inox/0020-launcher-branding.patch"
        "${_raw_github}/inox/0012-branding.patch"
        "${_raw_github}/patches/vaapi-fix.patch"
        "${_raw_github}/patches/add-missing-include-for-unique_ptr.patch"
        "${_raw_github}/patches/dns_util-make-DohUpgradeEntry-non-const.patch"
        "${_raw_github}/patches/fix-shutdown-crash-in-ProfileManager.patch"
        "${_raw_github}/patches/chromium-system-icu.patch"
        "${_raw_github}/patches/chromium-system-zlib.patch"
        "${_raw_github}/patches/fix-spammy-unique-font-matching-log.patch"
        "${_raw_github}/patches/chromium-widevine.patch"
        "${_raw_github}/patches/chromium-skia-harmony.patch")
sha256sums=('8df6ffca4087fc43e7d0443acc4f758399b248e96482705bd4fe7e88d239eb56'
            '04917e3cd4307d8e31bfb0027a5dce6d086edb10ff8a716024fbb8bb0c7dccf1'
            'SKIP'
            'c11ceb71833556abb58d0780562f59aadeb81a1cc599167edf6a71b31e335935'
            '7c6b7553ce2eda106e234b55386df14755e424285d02f6f0d92e9ae8467f75a0'
            'c56b3c8e6ff0ad644edf818b276799d9591e6f72b54f862970ce07a1a18598d5'
            '38ebabfb8f15a14d7feed1c5210dbcdcc1768cba08e9b3b5031ee588752ddc58'
            '71471fa4690894420f9e04a2e9a622af620d92ac2714a35f9a4c4e90fa3968dd'
            '4a533acefbbc1567b0d74a1c0903e9179b8c59c1beabe748850795815366e509'
            '7b88830c5e0e9819f514ad68aae885d427541a907e25607e47dee1b0f38975fd'
            '8c10e3b03b13555b461add586422472e0a96d3af49a078d6d952bc0719ba9d94'
            'cc08b771d83b7434c3173c27419bc7d1d4ee375256f3169ef2b9333ba1f2beeb'
            '53a1e8da18069eb4d6ab3af9c923c22a0f020241a4839c3140e3601052ddf6ff'
            '896993987d4ef9f0ac7db454f288117316c2c80ed0b6764019afd760db222dad'
            '3df9b3bbdc07fde63d9e400954dcc6ab6e0e5454f0ef6447570eef0549337354'
            '7e8f34e146284aa63d34d50663e52a94f8cbeaaa431ba27bdc948592dd930662'
            '777d342aac9bd8c5fd359b95e6bfd4d667a8d69c9fde52141c5c7829618e7b22'
            '9256123898cbdd4da4a111e5aa8752d5c6c2c07e59ca8677751791dd3321f6a9'
            '49052e8aa630c4aa57bf46823edc32b7b309493275163c3bb3f9fd390c73356e'
            '69694ab12a5ced389916c0c5e8c7bdc191544f576b134ddfb2fe9d4ed9ec4494'
            '4f81612c28957987f7344d8ce2b95a4a63136a8319c9751819436b11c62df057'
            'e73cc2ee8d3ea35aab18c478d76fdfc68ca4463e1e10306fa1e738c03b3f26b5'
            'eb67eda4945a89c3b90473fa8dc20637511ca4dcb58879a8ed6bf403700ca9c8'
            '6fbffe59b886195b92c9a55137cef83021c16593f49714acb20023633e3ebb19'
            'd081f2ef8793544685aad35dea75a7e6264a2cb987ff3541e6377f4a3650a28b'
            '771292942c0901092a402cc60ee883877a99fb804cb54d568c8c6c94565a48e1')

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
  [libjpeg]=libjpeg
  #[libpng]=libpng    # https://crbug.com/752403#c10
  #[libvpx]=libvpx    # https://github.com/webmproject/libvpx/commit/5a0242ba5c
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
  cd "$srcdir/chromium-${pkgver}"

  # Allow building against system libraries in official builds
  sed -i 's/OFFICIAL_BUILD/GOOGLE_CHROME_BUILD/' \
    tools/generate_shim_headers/generate_shim_headers.py

  # https://crbug.com/893950
  sed -i -e 's/\<xmlMalloc\>/malloc/' -e 's/\<xmlFree\>/free/' \
    third_party/blink/renderer/core/xml/*.cc \
    third_party/blink/renderer/core/xml/parser/xml_document_parser.cc \
    third_party/libxml/chromium/libxml_utils.cc

  msg2 'Applying archlinux patches'

  # Fix VA-API on Intel and Nvidia
  patch -Np1 -i ../vaapi-fix.patch

  # Missing include in third_party/blink/public/platform/web_rtc_rtp_source.h
  patch -Np1 -i ../add-missing-include-for-unique_ptr.patch

  # https://crbug.com/957519#c23
  patch -Np1 -i ../dns_util-make-DohUpgradeEntry-non-const.patch

  # https://crbug.com/1005244
  patch -Np1 -i ../fix-shutdown-crash-in-ProfileManager.patch

  # Fixes from Gentoo
  patch -Np1 -i ../chromium-system-icu.patch
  patch -Np1 -i ../chromium-system-zlib.patch

  # https://crbug.com/1005508
  patch -Np1 -i ../fix-spammy-unique-font-matching-log.patch

  # Load Widevine CDM if available
  #patch -Np1 -i ../chromium-widevine.patch

  # https://crbug.com/skia/6663#c10
  patch -Np0 -i ../chromium-skia-harmony.patch

  # Ungoogled chromium stuff
  _ungoogled_repo="$srcdir/$_pkgname"

  cd ${_ungoogled_repo}
  patch -Np1 -i ${srcdir}/848.patch
  cd "$srcdir/chromium-${pkgver}"

  _utils="${_ungoogled_repo}/utils"
  msg2 'Applying ungoogled chromium patches'
  # Prune binaries
  python "$_utils/prune_binaries.py" ./ "$_ungoogled_repo/pruning.list"
  # Patches themselves
  python "$_utils/patches.py" apply ./ "$_ungoogled_repo/patches"
  # domain substitution
  python "$_utils/domain_substitution.py" apply -r "$_ungoogled_repo/domain_regex.list" -f "$_ungoogled_repo/domain_substitution.list" -c domainsubcache.tar.gz ./

  # inox/vanadium
  patch -Np1 -i ../0012-branding.patch
  patch -Np1 -i ../0009-disable-seed-based-field-trials.patch

  # Force script incompatible with Python 3 to use /usr/bin/python2
  sed -i '1s|python$|&2|' third_party/dom_distiller_js/protoc_plugins/*.py

  mkdir -p third_party/node/linux/node-linux-x64/bin
  ln -s /usr/bin/node third_party/node/linux/node-linux-x64/bin/

  # Remove bundled libraries for which we will use the system copies; this
  # *should* do what the remove_bundled_libraries.py script does, with the
  # added benefit of not having to list all the remaining libraries
  local _lib
  for _lib in ${_unwanted_bundled_libs[@]}; do
    find "third_party/$_lib" -type f \
      \! -path "third_party/$_lib/chromium/*" \
      \! -path "third_party/$_lib/google/*" \
      \! -path 'third_party/yasm/run_yasm.py' \
      \! -regex '.*\.\(gn\|gni\|isolate\)' \
      -delete
  done

  python2 build/linux/unbundle/replace_gn_files.py \
    --system-libraries "${!_system_libs[@]}"

  # Applying Chromium launcher patches
  cd "$srcdir/chromium-launcher-$_launcher_ver"
  patch -Np1 -i ../0020-launcher-branding.patch
}

build() {
  make -C chromium-launcher-$_launcher_ver

  cd "$srcdir/chromium-${pkgver}"

  if check_buildoption ccache y; then
    # Avoid falling back to preprocessor mode when sources contain time macros
    export CCACHE_SLOPPINESS=time_macros
  fi

  export CC=clang
  export CXX=clang++
  export AR=ar
  export NM=nm

  # Ungoogled Chromium stuff
  _ungoogled_repo="$srcdir/$_pkgname"
  mkdir -p out/Release
  # Assemble GN flags
  cp "$_ungoogled_repo/flags.gn" "out/Release/args.gn"
  printf '\n' >> "out/Release/args.gn"
  cat "$srcdir/flags.archlinux.gn" >> "out/Release/args.gn"

  if check_option strip y; then
    _flags+=('symbol_level=0')
  fi

  # Facilitate deterministic builds (taken from build/config/compiler/BUILD.gn)
  CFLAGS+='   -Wno-builtin-macro-redefined'
  CXXFLAGS+=' -Wno-builtin-macro-redefined'
  CPPFLAGS+=' -D__DATE__=  -D__TIME__=  -D__TIMESTAMP__='

  # Do not warn about unknown warning options
  CFLAGS+='   -Wno-unknown-warning-option'
  CXXFLAGS+=' -Wno-unknown-warning-option'

  gn gen out/Release --script-executable=/usr/bin/python2
  ninja -C out/Release chrome chrome_sandbox chromedriver
}

package() {
  cd chromium-launcher-$_launcher_ver
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -Dm644 LICENSE \
    "$pkgdir/usr/share/licenses/$pkgname/LICENSE.launcher"

  cd "$srcdir/chromium-${pkgver}"

  install -D out/Release/chrome "$pkgdir/usr/lib/$pkgname/$pkgname"
  install -Dm4755 out/Release/chrome_sandbox "$pkgdir/usr/lib/$pkgname/chrome-sandbox"
  install -D out/Release/chromedriver "$pkgdir/usr/lib/$pkgname/inoxdriver"
  ln -s /usr/lib/$pkgname/inoxdriver "$pkgdir/usr/bin/inoxdriver"

  # TODO: do we need to change this for inox?
  install -Dm644 ../inox-drirc-disable-10bpc-color-configs.conf \
    "$pkgdir/usr/share/drirc.d/10-$pkgname.conf"

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
    out/Release/{chrome_{100,200}_percent,resources}.pak \
    out/Release/*.bin \
    "$pkgdir/usr/lib/$pkgname/"
  install -Dm644 -t "$pkgdir/usr/lib/$pkgname/locales" out/Release/locales/*.pak

  if [[ -z ${_system_libs[icu]+set} ]]; then
    cp out/Release/icudtl.dat "$pkgdir/usr/lib/$pkgname/"
  fi

  for size in 16 22 24 32 48 64 128 256; do
    install -Dm644 "../product_logo_$size.png" \
      "$pkgdir/usr/share/icons/hicolor/${size}x${size}/apps/$pkgname.png"
  done

  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

# vim:set ts=2 sw=2 et:
