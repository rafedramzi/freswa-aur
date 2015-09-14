# Maintainer: Frederik Schwan <frederik dot schwan at linux dot com>

pkgname=duperemove-git
pkgver=346.87046ec
pkgrel=1
pkgdesc="Btrfs extent deduplication utility"
arch=('x86_64' 'i686')
url="https://github.com/markfasheh/duperemove"
license=('GPL')
depends=('glib2' 'sqlite')
makedepends=('git')
conflicts=('duperemove')
source=("$pkgname"::'git://github.com/markfasheh/duperemove.git#branch=master')
md5sums=('SKIP')

pkgver() {
  cd ${pkgname}
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "$srcdir/$pkgname"
  make
}

package() {
  cd $srcdir/$pkgname
  make PREFIX=/usr SBINDIR=/usr/bin DESTDIR="${pkgdir}" install
}
