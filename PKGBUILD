# Maintainer: artist for Artix Linux

pkgname=sonic-win
_pkgname=kwin-x11
pkgver=6.5.4
_pkgtag=6.5.4
pkgrel=3
pkgdesc='An X11-only, lighter-weight fork of KWin'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-win'
license=('LGPL-2.0-or-later')
depends=(aurorae
         breeze
         gcc-libs
         glibc
         plasma-activities
         kauth
         kcmutils
         kcolorscheme
         kconfig
         kcoreaddons
         kcrash
         kdeclarative
         kdecoration
         kglobalaccel
         kglobalacceld
         kguiaddons
         ki18n
         kirigami
         kitemmodels
         knewstuff
         knighttime
         knotifications
         kpackage
         kquickcharts
         kscreenlocker
         kservice
         ksvg
         kwidgetsaddons
         kwindowsystem
         kxmlgui
         lcms2
         libcanberra
         libdisplay-info
         libdrm
         libepoxy
         libplasma=$pkgver
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
         qt6-wayland
         wayland
         xcb-util-cursor
         xcb-util-keysyms
         xcb-util-wm)
makedepends=(extra-cmake-modules
             git
             kdoctools
             libelogind
             plasma-wayland-protocols
             python
             wayland-protocols)
groups=(sonicde)
provides=($_pkgname $_pkgname-sonic)
conflicts=($_pkgname $_pkgname-sonic)
replaces=($_pkgname-sonic)
#source=("git+${url}.git#tag=${_pkgtag}")
#source=("git+${url}.git#commit=6b537a5596450514971412706e74b6dfadd36a57")
source=("${url}/archive/refs/tags/${_pkgtag}.tar.gz")
install="$pkgname.install"
options=(!debug)
sha256sums=('fce093b1ae4079604bb38996a99395134a102ecc76cb92a945e92e02b09337d4')

build() {
  cmake -B build -S $pkgname-$_pkgtag \
    -DCMAKE_INSTALL_LIBEXECDIR=lib \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build

  rm -r $pkgdir/usr/lib/systemd
}

