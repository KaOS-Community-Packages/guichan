pkgname=guichan
pkgver=0.8.2
pkgrel=1
pkgdesc="A portable C++ GUI library designed for games using Allegro, SDL and/or OpenGL."
arch=('x86_64')
url="http://guichan.sourceforge.net/"
license=('BSD')
makedepends=('sdl_image' 'allegro4' 'libgl' 'freeglut')
options=('!strip')
source=(http://guichan.googlecode.com/files/$pkgname-$pkgver.tar.gz)
sha256sums=('eedf206eae5201eaae027b133226d0793ab9a287bfd74c5f82c7681e3684eeab')

build() {
  cd "${srcdir}"/$pkgname-$pkgver

  CXXFLAGS="-g" ./configure --prefix=/usr
  make
}

package() {
  cd "${srcdir}"/$pkgname-$pkgver
  
  make prefix="${pkgdir}"/usr install

# Install the license, as required for BSD
  install -m644 -D COPYING "${pkgdir}"/usr/share/licenses/$pkgname/LICENSE
}