# Contributor: Antonio Rojas

pkgname=libkscreen2
pkgver=1.73
plasmaver=4.98.0
pkgrel=2
pkgdesc='KDE screen management software'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/extragear/libs/libkscreen'
license=('LGPL')
depends=('qt5-x11extras' 'libxrandr')
makedepends=('extra-cmake-modules')
source=("http://download.kde.org/unstable/plasma/$plasmaver/src/libkscreen-$pkgver.tar.xz")
md5sums=('f8399efac454840ccb312b6a106ac30e')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../libkscreen-$pkgver \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DLIB_INSTALL_DIR=lib \
    -DQT_PLUGIN_INSTALL_DIR=lib/qt/plugins \
    -DECM_MKSPECS_INSTALL_DIR=/usr/share/qt/mkspecs/modules \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
