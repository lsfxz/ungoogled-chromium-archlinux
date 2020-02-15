# Derived from PKGBUILD for Inox
# Original Inox PKGBUILD authors:
# Maintainer: Michael Egger <gcarq@archlinux.info>
# Contributor: Evangelos Foutras <evangelos@foutrelis.com>
# Contributor: Pierre Schmitz <pierre@archlinux.de>
# Contributor: Jan "heftig" Steffens <jan.steffens@gmail.com>
# Contributor: Daniel J Griffiths <ghost1227@archlinux.us>

pkgname=inox
_pkgname=ungoogled-chromium
pkgver=80.0.3987.106
pkgrel=1
_launcher_ver=6
_ungoogled_commit=52cd482e7477d1131139c82ac2c41c5b89f59c8c
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
        https://github.com/Eloston/ungoogled-chromium/pull/934.patch
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
        "cros-search-service-Include-cmath-for-std-pow.patch::${_arch_svn}/cros-search-service-Include-cmath-for-std-pow.patch?h=packages/chromium"
        "move-RemoteTreeNode-declaration.patch::${_arch_svn}/move-RemoteTreeNode-declaration.patch?h=packages/chromium"
        "fix-shim-header-generation-when-unbundling-ICU.patch::${_arch_svn}/fix-shim-header-generation-when-unbundling-ICU.patch?h=packages/chromium"
        "fix-building-with-system-zlib.patch::${_arch_svn}/fix-building-with-system-zlib.patch?h=packages/chromium"
        "remove-verbose-logging-in-local-unique-font-matching.patch::${_arch_svn}/remove-verbose-logging-in-local-unique-font-matching.patch?h=packages/chromium"
        "fix-building-with-unbundled-libxml.patch::${_arch_svn}/fix-building-with-unbundled-libxml.patch?h=packages/chromium"
        "rename-Relayout-in-DesktopWindowTreeHostPlatform.patch::${_arch_svn}/rename-Relayout-in-DesktopWindowTreeHostPlatform.patch?h=packages/chromium"
        "rebuild-Linux-frame-button-cache-when-activation.patch::${_arch_svn}/rebuild-Linux-frame-button-cache-when-activation.patch?h=packages/chromium"
        "vaapi-fix.patch::https://aur.archlinux.org/cgit/aur.git/plain/vaapi-fix.patch?h=chromium-vaapi"
        "chromium-widevine.patch::${_arch_svn}/chromium-widevine.patch?h=packages/chromium"
        "chromium-skia-harmony.patch::${_arch_svn}/chromium-skia-harmony.patch?h=packages/chromium"
        "sync-enable-USSPasswords-by-default.patch::${_arch_svn}/sync-enable-USSPasswords-by-default.patch?h=packages/chromium")
sha256sums=('2ead924b4414a8a5f085fa0e0df56563ef41bd4290cc403c05d5beec238cbe82'
            'cdf6be61a5bd8ee4db05c0909bf062d08940651e6619cbaa1f451e56c978feb4'
            '04917e3cd4307d8e31bfb0027a5dce6d086edb10ff8a716024fbb8bb0c7dccf1'
            'SKIP'
            '60086ecba6ffd3bd9c218b6f6f78c6e8cf8ff2875be6299cf40d0b3c0bab05a1'
            '595386d403e7ab3ebce77037ecf2fa5c40ec4d07e2bd3cbfcf72857467e004d3'
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
            'd0ff7f9dd4b7bf5bcb70a191f8d7ace292a936cf2123e24ce005ea84de118816'
            '0a8d1af2a3734b5f99ea8462940e332db4acee7130fe436ad3e4b7ad133e5ae5'
            '21f631851cdcb347f40793485b168cb5d0da65ae26ae39ba58d624c66197d0a5'
            'e477aa48a11ca4d53927f66a9593567fcd053325fb38af30ac3508465f1dd1f6'
            '18276e65c68a0c328601b12fefb7e8bfc632346f34b87e64944c9de8c95c5cfa'
            '5bc775c0ece84d67855f51b30eadcf96fa8163b416d2036e9f9ba19072f54dfe'
            'e530d1b39504c2ab247e16f1602359c484e9e8be4ef6d4824d68b14d29a7f60b'
            'ae3bf107834bd8eda9a3ec7899fe35fde62e6111062e5def7d24bf49b53db3db'
            '46f7fc9768730c460b27681ccf3dc2685c7e1fd22d70d3a82d9e57e3389bb014'
            '0ec6ee49113cc8cc5036fa008519b94137df6987bf1f9fbffb2d42d298af868a'
            '709e2fddba3c1f2ed4deb3a239fc0479bfa50c46e054e7f32db4fb1365fed070'
            '771292942c0901092a402cc60ee883877a99fb804cb54d568c8c6c94565a48e1'
            '08ef82476780e0864b5bf7f20eb19db320e73b9a5d4f595351e12e97dda8746f')

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
    third_party/libxml/chromium/*.cc

  msg2 'Applying archlinux patches'

  # Fix VA-API on Intel and Nvidia
  patch -Np1 -i ../vaapi-fix.patch

  # https://crbug.com/957519
  patch -Np1 -i ../cros-search-service-Include-cmath-for-std-pow.patch
  patch -Np1 -i ../move-RemoteTreeNode-declaration.patch


  # https://crbug.com/1027929
  patch -Np1 -i ../sync-enable-USSPasswords-by-default.patch

  # https://crbug.com/989153
  patch -Np1 -i ../fix-shim-header-generation-when-unbundling-ICU.patch

  # https://crbug.com/977964
  patch -Np1 -i ../fix-building-with-system-zlib.patch

  # https://crbug.com/1005508
  patch -Np1 -i ../remove-verbose-logging-in-local-unique-font-matching.patch

  # https://crbug.com/1043042
  patch -Np1 -i ../fix-building-with-unbundled-libxml.patch

  # https://crbug.com/1049258
  patch -Np1 -i ../rename-Relayout-in-DesktopWindowTreeHostPlatform.patch
  patch -Np1 -i ../rebuild-Linux-frame-button-cache-when-activation.patch

  # Load bundled Widevine CDM if available (see chromium-widevine in the AUR)
  # M79 is supposed to download it as a component but it doesn't seem to work
  # patch -Np1 -i ../chromium-widevine.patch

  # https://crbug.com/skia/6663#c10
  patch -Np0 -i ../chromium-skia-harmony.patch

  # Ungoogled chromium stuff
  _ungoogled_repo="$srcdir/$_pkgname"

  cd ${_ungoogled_repo}
  patch -Np1 -i ${srcdir}/934.patch
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
  cd chrome
  patch -Np1 -i ../../0012-branding.patch
  cd ..
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
  ninja -j 4 -C out/Release chrome chrome_sandbox chromedriver
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
