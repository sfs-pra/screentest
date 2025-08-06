# Maintainer: sfslinux@gmail.com

pkgname=screentest
pkgver=3.0.r5.gf30e3fc
pkgrel=3
pkgdesc="tesing the quality of CRT/LCD screens"
arch=('x86_64')
#url="https://github.com/TobiX/screentest"
url="https://github.com/sfs-pra/screentest"
license=('GPL2')
depends=('gtk3' )
makedepends=('meson')
source=(git+$url)
sha256sums=('SKIP')

pkgver() {
  cd $pkgname
  git describe --long | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
  cd $pkgname
  meson build --prefix /usr 
  meson compile -C build
}

package() {
  cd $pkgname
  DESTDIR="$pkgdir" meson install -C build
}
