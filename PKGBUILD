# Maintainer: Oliver Giles <web ohwg net>
pkgname=sequeljoe
pkgver=0.4
pkgrel=3
pkgdesc="SQL database administration tool"
arch=('i686' 'x86_64')
url="http://sequeljoe.ohwg.net"
license=('GPL3')
groups=()
depends=('qt5-base' 'libssh2' 'libnotify')
optdepends=(
   'libmariadbclients: MySQL/MariaDB support'
   'sqlite: sqlite support'
   'postgresql-libs: PostgreSQL support'
)
makedepends=('cmake')
options=('strip')
source=("https://github.com/ohwgiles/sequeljoe/archive/$pkgver.zip")
sha256sums=('e031547b5c3159105678f93d713fa4dac6acd3f75af3d2c6c95cc6ced22459bb')

build() {
	cd "$srcdir/$pkgname-$pkgver"
	cmake -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release src
	make
}

package() {
	cd "$srcdir/$pkgname-$pkgver"
	make DESTDIR="$pkgdir/" install
}

