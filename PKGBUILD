# Derived from PKGBUILD for Inox
# Original Inox PKGBUILD authors:
# Maintainer: Michael Egger <gcarq@archlinux.info>
# Contributor: Evangelos Foutras <evangelos@foutrelis.com>
# Contributor: Pierre Schmitz <pierre@archlinux.de>
# Contributor: Jan "heftig" Steffens <jan.steffens@gmail.com>
# Contributor: Daniel J Griffiths <ghost1227@archlinux.us>

pkgname=inox
_pkgname=ungoogled-chromium
pkgver=79.0.3945.117
pkgrel=1
_launcher_ver=6
_ungoogled_commit=e7d8f6637e11b6980a68d35995bc7830d2fcbb19
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
            'org.freedesktop.secrets: password storage backend on GNOME / Xfce'
            'kwallet: for storing passwords in KWallet'
            'libva-intel-driver: for hardware video acceleration with Intel GPUs'
            'libva-mesa-driver: for hardware video acceleration with AMD/ATI GPUs'
            'libva-vdpau-driver: for hardware video acceleration with NVIDIA GPUs')
provides=('inox')
conflicts=('inox')
_raw_github=https://raw.githubusercontent.com/lsfxz/ungoogled-chromium-archlinux/inox
_arch_svn=https://git.archlinux.org/svntogit/packages.git/plain/trunk
source=(https://commondatastorage.googleapis.com/chromium-browser-official/chromium-${pkgver}.tar.xz
        chromium-launcher-$_launcher_ver.tar.gz::https://github.com/foutrelis/chromium-launcher/archive/v$_launcher_ver.tar.gz
        "ungoogled-chromium::git+https://github.com/Eloston/ungoogled-chromium.git#commit=${_ungoogled_commit}"
        "https://raw.githubusercontent.com/GrapheneOS/Vanadium/10/0009-disable-seed-based-field-trials.patch"
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
        "vaapi-fix.patch::https://aur.archlinux.org/cgit/aur.git/plain/vaapi-fix.patch?h=chromium-vaapi"
        "launch_manager.h-uses-std-vector.patch::${_arch_svn}/launch_manager.h-uses-std-vector.patch?h=packages/chromium"
        "include-algorithm-to-use-std-lower_bound.patch::${_arch_svn}/include-algorithm-to-use-std-lower_bound.patch?h=packages/chromium"
        "chromium-system-hb.patch::${_arch_svn}/chromium-system-hb.patch?h=packages/chromium"
        "chromium-system-icu.patch::${_arch_svn}/chromium-system-icu.patch?h=packages/chromium"
        "chromium-system-zlib.patch::${_arch_svn}/chromium-system-zlib.patch?h=packages/chromium"
        "fix-spammy-unique-font-matching-log.patch::${_arch_svn}/fix-spammy-unique-font-matching-log.patch?h=packages/chromium"
        "chromium-widevine.patch::${_arch_svn}/chromium-widevine.patch?h=packages/chromium"
        "chromium-skia-harmony.patch::${_arch_svn}/chromium-skia-harmony.patch?h=packages/chromium"
        "icu65.patch::${_arch_svn}/icu65.patch?h=packages/chromium")
sha256sums=('4d960e8bd790cc1c8e7f0632790424957c4996a8a91b9d899eb572acec854ef1'
            '04917e3cd4307d8e31bfb0027a5dce6d086edb10ff8a716024fbb8bb0c7dccf1'
            'SKIP'
            '7b4e881f9eb89482a102e74dc626c931f11347bee48469c5273b5ee0fd285b73'
            'cb1092585d98c8f98d1b8800f9a88d664a40ebe61efeb3d3363ad51dc186643c'
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
            '0ec6ee49113cc8cc5036fa008519b94137df6987bf1f9fbffb2d42d298af868a'
            'bd0fae907c451252e91c4cbf1ad301716bc9f8a4644ecc60e9590a64197477d3'
            '1f906676563e866e2b59719679e76e0b2f7f082f48ef0593e86da0351a586c73'
            'c0ad3fa426cb8fc1a237ddc6309a6b2dd4055bbe41dd07f50071ee61f969b81a'
            'e73cc2ee8d3ea35aab18c478d76fdfc68ca4463e1e10306fa1e738c03b3f26b5'
            'eb67eda4945a89c3b90473fa8dc20637511ca4dcb58879a8ed6bf403700ca9c8'
            '6fbffe59b886195b92c9a55137cef83021c16593f49714acb20023633e3ebb19'
            'd081f2ef8793544685aad35dea75a7e6264a2cb987ff3541e6377f4a3650a28b'
            '771292942c0901092a402cc60ee883877a99fb804cb54d568c8c6c94565a48e1'
            '1de9bdbfed482295dda45c7d4e323cee55a34e42f66b892da1c1a778682b7a41')

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

  # https://crbug.com/819294
  patch -Np1 -i ../launch_manager.h-uses-std-vector.patch
  patch -Np1 -i ../include-algorithm-to-use-std-lower_bound.patch

  # https://crbug.com/1014272
  patch -Np1 -i ../icu65.patch

  # Fixes from Gentoo
  patch -Np1 -i ../chromium-system-icu.patch
  patch -Np1 -i ../chromium-system-zlib.patch
  patch -Np1 -i ../chromium-system-hb.patch

  # https://crbug.com/1005508
  patch -Np1 -i ../fix-spammy-unique-font-matching-log.patch

  # Load bundled Widevine CDM if available (see chromium-widevine in the AUR)
  # M79 is supposed to download it as a component but it doesn't seem to work
  patch -Np1 -i ../chromium-widevine.patch

  # https://crbug.com/skia/6663#c10
  patch -Np0 -i ../chromium-skia-harmony.patch

  # Ungoogled chromium stuff
  _ungoogled_repo="$srcdir/$_pkgname"

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

  local _flags=(
  '')
  # Ungoogled Chromium stuff
  _ungoogled_repo="$srcdir/$_pkgname"
  mkdir -p out/Release
  # Assemble GN flags
  cp "$_ungoogled_repo/flags.gn" "out/Release/args.gn"
  printf '\n' >> "out/Release/args.gn"
  cat "$srcdir/flags.archlinux.gn" >> "out/Release/args.gn"

  if [[ -n ${_system_libs[icu]+set}  ]]; then
    _flags+=('icu_use_data_file=false')
  fi

  if check_option strip y; then
    _flags+=('symbol_level=0')
  fi

  _flags+=('enable_widevine=true')

  # Facilitate deterministic builds (taken from build/config/compiler/BUILD.gn)
  CFLAGS+='   -Wno-builtin-macro-redefined'
  CXXFLAGS+=' -Wno-builtin-macro-redefined'
  CPPFLAGS+=' -D__DATE__=  -D__TIME__=  -D__TIMESTAMP__='

  # Do not warn about unknown warning options
  CFLAGS+='   -Wno-unknown-warning-option'
  CXXFLAGS+=' -Wno-unknown-warning-option'

  for flag in ${_flags[*]}; do
    echo "${flag}" >> "out/Release/args.gn"
  done

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
