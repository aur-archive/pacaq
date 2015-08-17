# Maintainer: archtux <antonio dot arias99999 at gmail dot com>

pkgname=pacaq
pkgver=0.1.1
pkgrel=2
pkgdesc="Chess game visualizing and analysis tool with Qt based GUI."
arch=('i686' 'x86_64')
url="http://pacaq.sourceforge.net/"
license=('GPL2')
depends=('qt4')
source=(http://prdownloads.sourceforge.net/$pkgname/$pkgname-$pkgver.tar.gz)
md5sums=('a8f8593a81f79829a1c425207ff36b6b')

build() {
  cd $srcdir

  # Fix compilation
  sed -i 's_debug_release_' pacaq.pro

  qmake4
  make
}

package() {

  # Binary
  install -Dm755 pacaq $pkgdir/usr/bin/pacaq

  # Desktop icon 
  sed -i 's_Games_Game_' pacaq.desktop
  install -Dm644 rook-48x48.png $pkgdir/usr/share/pixmaps/pacaq.png
  install -Dm644 pacaq.desktop $pkgdir/usr/share/applications/pacaq.desktop
}