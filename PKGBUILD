# Mantainer:   Attilio Priolo <attilio.priolo@gmail.com>
# Contributor: Renato Garcia <fgar.renato@gmail.com>
# Contributor: Yannick Poirier <contact@yannickpoirier.fr>
# This PKGBUILD is built upon the original version made by the contributors. The current mantainer 
# has only written the patch to let the package compile.

pkgname=stage3
pkgrealname=stage
pkgver=3.2.2
pkgrel=1
pkgdesc="Fast and scalable robot simulator"
arch=('i686' 'x86_64')
url="http://playerstage.sourceforge.net"
license=('GPL')
depends=('fltk' 'player' 'libpng')
conflicts=('stage' 'stage-git')
makedepends=('cmake')
source=(http://downloads.sourceforge.net/project/playerstage/${pkgrealname/s/S}/${pkgver}/${pkgrealname/s/S}-${pkgver}-Source.tar.gz
	${pkgrealname/s/S}-${pkgver}.patch)

md5sums=('ca93c7c9746354679829092640c49ec6'
	 '34c6adb4b38218ee0c1cfa8edcc283c8')

build() {
  cd $srcdir/${pkgrealname/s/S}-$pkgver-Source
  patch -p1 -i $srcdir/${pkgrealname/s/S}-${pkgver}.patch
  cmake . -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd $srcdir/${pkgrealname/s/S}-$pkgver-Source
  make DESTDIR="${pkgdir}" install
}
