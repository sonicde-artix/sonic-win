# Maintainer: artist for Artix Linux

pkgname=sonic-win
_pkgname=kwin-x11
pkgver=6.6.2.1
_pkgtag=$pkgver
_plasmaver=$(echo $pkgver | cut -f1-3 -d'.')
pkgrel=1
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
         libplasma=$_plasmaver
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
         libelogind
         wayland
         xcb-util-cursor
         xcb-util-keysyms
         xcb-util-wm)
makedepends=(extra-cmake-modules
             git
             kdoctools
             plasma-wayland-protocols
             python
             wayland-protocols)
groups=(sonicde)
provides=($_pkgname)
conflicts=($_pkgname)
source=("${url}/archive/refs/tags/${_pkgtag}.tar.gz")
#source=("git+${url}.git#tag=$pkgver")
install="$pkgname.install"
options=(!debug)
sha256sums=('781e56db40ff06c204730cd4e67461a963457814e56e2a172fd1dfb12eef5c7a')

build() {
  cmake -B build -S $pkgname-$_pkgtag \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_LIBEXECDIR=lib \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build

  rm -r $pkgdir/usr/lib/systemd
}

