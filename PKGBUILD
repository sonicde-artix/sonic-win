# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>

pkgname=sonic-win
pkgver=6.6.5
pkgrel=4
pkgdesc='An X11-only, lighter-weight fork of KWin'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-win'
license=('LGPL-2.0-or-later')
depends=(aurorae
         breeze
         elogind
         glibc
         kcmutils
         kcolorscheme
         kconfig
         kcrash
         kdeclarative
         kguiaddons
         ki18n
         kitemmodels
         knewstuff
         knighttime
         knotifications
         kpackage
         kquickcharts
         kservice
         ksvg
         kwidgetsaddons
         kxmlgui
         lcms2
         libcanberra
         libdisplay-info
         libdrm
         libepoxy
         libgcc
         libqaccessibilityclient-qt6
         libx11
         libxcb
         libxi
         libxkbcommon
         libxkbcommon-x11
         mesa
         qt6-5compat
         qt6-base
         qt6-declarative
         qt6-sensors
         qt6-svg
         qt6-tools
         sonic-activities
         sonic-frameworks-auth
         sonic-frameworks-auth
         sonic-frameworks-core-addons
         sonic-frameworks-core-addons
         sonic-frameworks-keybind
         sonic-frameworks-quick-ui
         sonic-frameworks-quick-ui
         sonic-frameworks-windowsystem
         sonic-interface-libraries
         sonic-keybind-daemon
         sonic-screenlocker
         xcb-util-cursor
         xcb-util-keysyms
         xcb-util-wm)
makedepends=(extra-cmake-modules
             kdoctools
             python)
groups=(sonicde)
conflicts=(kwin-x11)
replaces=(kwin-x11)
provides=(kwin-x11)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
options=(!debug)
sha256sums=('d9d1539b8a962dda9c9999326202f05b4a3eb484ffee97b620d33e3e9e73290a')

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_LIBEXECDIR=lib \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build

  rm -r $pkgdir/usr/lib/systemd
}
