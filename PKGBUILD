# Maintainer: xquiet <matteo@xquiet.eu>
gitdate=20130225
pkgname=yalib
pkgver=1.0
pkgrel=0.git$gitdate.1
pkgdesc="Shared library used by YaFlight and YaInstall"
arch=('i686'
      'x86_64')
url="http://yaflight.altervista.org"
license=('GPL3')
depends=('qt4>4.8.3')
makedepends=('qt4>=4.8.3')
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=($pkgname-$pkgver-$pkgrel.tar.bz2::https://bitbucket.org/_pmat_/yalib/downloads/$pkgname-$pkgver-$gitdate.tar.bz2
	$pkgname-pro.patch)
noextract=()
md5sums=('249c80427906acdd0d0c0636cd3e73f0'
         'a37bb15b324d3d45d3fc9a923936be23') # generate with makepkg -g

build() {
  cd "$srcdir/$pkgname-$pkgver-$gitdate"
  patch -p1 -i ../../$pkgname-pro.patch
  # force qt4 usage
  qmake-qt4
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver-$gitdate"
  make INSTALL_ROOT="$pkgdir" install
}
