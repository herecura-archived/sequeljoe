# Maintainer: Oliver Giles <web ohwg net>
pkgname=sequeljoe
pkgver=0.1
pkgrel=1
pkgdesc="SQL database administration tool"
arch=('i686 x86_64')
url="http://sequeljoe.ohwg.net"
license=('GPL3')
groups=()
depends=('qt5-base' 'libssh2' 'libnotify')
optdepends=(
   'libmariadbclients: MySQL/MariaDB support'
   'sqlite: sqlite support'
)
makedepends=('cmake')
options=('strip')
source=("https://github.com/ohwgiles/sequeljoe/archive/$pkgver.zip")
md5sums=('9b659272e4bcf042375e2487775ddef4')

build() {
	cd "$srcdir/$pkgname-$pkgver"
	cmake -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release src
	make -j4
}

package() {
	cd "$srcdir/$pkgname-$pkgver"
	make DESTDIR="$pkgdir/" install
}

