# Maintainer: Antonio Rojas

pkgname=sddm-kcm
pkgver=5.1.95
pkgrel=1
pkgdesc="SDDM configuration module for KDE"
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/kdereview/sddm-kcm/'
license=('GPL')
groups=('plasma-next')
depends=('sddm' 'libxcursor' 'kio')
makedepends=('extra-cmake-modules' 'kdoctools' 'qt5-tools')
source=("http://download.kde.org/unstable/plasma/$pkgver/$pkgname-$pkgver.tar.xz")
md5sums=('1277b596b7f0d0013674ad7e39ed37ff')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../$pkgname-$pkgver \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DLIB_INSTALL_DIR=lib \
    -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
    -DSYSCONF_INSTALL_DIR=/etc
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}

