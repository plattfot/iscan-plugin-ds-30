# Maintainer: ItsTheSource <itsthesource at gmail dot com>
# Contributor: ItsTheSource <itsthesource at gmail dot com>

pkgname=iscan-plugin-ds-30
pkgver=1.0.0
pkgrel=3
pkgdesc="iscan plugin for Epson WorkForce DS-30"
arch=('x86_64')
url="http://download.ebz.epson.net/dsc/search/01/search/?OSC=LX"
license=('custom:AVASYSPL')
depends=('iscan-data' 'iscan')
install=ds-30.install
changelog=ChangeLog
source=("https://download2.ebz.epson.net/iscan/plugin/ds-30/deb/x64/iscan-ds-30-bundle-1.0.1.x64.deb.tar.gz")
md5sums=('131fd1f68267b39003b6a13187a97113')

build(){
  root_pkg=iscan-ds-30-bundle-1.0.1.x64.deb
  cd $srcdir
  tar -xf $root_pkg.tar.gz
  cd $root_pkg/plugins
  ar vx ${pkgname}_${pkgver}-${pkgrel}_amd64.deb
  tar -zxvf data.tar.gz -C $srcdir
}

package(){
  install -d $pkgdir/usr/lib/iscan
  install -m755 $srcdir/usr/lib/iscan/libiscan-plugin-ds-30.so.0.0.0 $pkgdir/usr/lib/iscan/
  install -m755 $srcdir/usr/lib/iscan/libiscan-plugin-ds-30.so.0 $pkgdir/usr/lib/iscan/
  install -m755 $srcdir/usr/lib/iscan/libiscan-plugin-ds-30.so $pkgdir/usr/lib/iscan/
  install -d $pkgdir/usr/share/licenses/$pkgname/
  install -m644 $srcdir/usr/share/doc/$pkgname/{AVASYSPL.en.txt,AVASYSPL.ja.txt,copyright} $pkgdir/usr/share/licenses/$pkgname/
}

