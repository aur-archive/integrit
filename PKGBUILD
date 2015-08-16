# Maintainer: Michael Rolf <mi.rolf@gmx.net>

pkgname=integrit
pkgver=4.1
pkgrel=3
pkgdesc="Simple yet secure file verification system with features that make sense"
arch=('i686' 'x86_64')
url='http://sourceforge.net/projects/integrit'
license=('GPL')
install=integrit.install
source=(http://downloads.sourceforge.net/sourceforge/${pkgname}/${pkgname}-${pkgver}.tar.gz)
md5sums=('f51a5b558981a5d90e7d6f4e7e269a46')
optdepends=(
  'bash: for using the example scripts'
  'perl: for using the example scripts'
)

build() {
  cd $srcdir/$pkgname-$pkgver
  ./configure --prefix=$pkgdir/usr --sbindir=$pkgdir/usr/bin --mandir=$pkgdir/usr/share/man --infodir=$pkgdir/usr/share/info
  make
  cd utils
  make
}

package() {
  cd $srcdir/$pkgname-$pkgver
  make install

  # also install the examples
  /bin/install -d $pkgdir/usr/share/doc/integrit/examples
  /bin/install -m 644 examples/* $pkgdir/usr/share/doc/integrit/examples/
}

