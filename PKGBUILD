pkgname=bytekit
pkgver=0.1.1
pkgrel=2
pkgdesc="PHP extension that provides a userspace representation of the opcodes generated by the Zend engine compiler"
arch=('i686' 'x86_64')
url="http://www.bytekit.org/"
license=('custom')
depends=('php')
source=(http://www.bytekit.org/download/bytekit-$pkgver.tgz)
md5sums=('83d0a325713201947aec441f30be58d8')

build() {
   cd $startdir/src/$pkgname-$pkgver/
   phpize
   ./configure
   make
   mkdir -p $startdir/pkg/usr/lib/php/modules/
   install -D -m644 modules/bytekit.so $startdir/pkg/usr/lib/php/modules/ || return 1
   mkdir -p $startdir/pkg/etc/php/conf.d/
   echo extension=bytekit.so > $startdir/pkg/etc/php/conf.d/bytekit.ini
}
