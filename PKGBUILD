# Maintainer: sfslinux@gmail.com

pkgname=screentest
pkgver=r86.f30e3fc
pkgrel=1
pkgdesc="Tesing the quality of CRT/LCD screens"
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
#  git describe --long | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
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
