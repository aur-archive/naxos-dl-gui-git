# Maintainer: Carlos Manuel <fis.carlosmanuel@gmail.com>
pkgname=naxos-dl-gui-git
pkgver=r129.c865cc4
pkgrel=1
pkgdesc="A downloader for the NML service"
arch=('i686' 'x86_64')
url="https://github.com/cmrm/Naxos-Dl"
license=('Public domain')
depends=('wxgtk' 'curl' 'imagemagick' 'python2' 'python2-beautifulsoup4' 'mutagen' 'python2-lxml')
makedepends=('git')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
source=('naxos-dl-gui-git::git://github.com/cmrm/Naxos-Dl.git')
md5sums=('SKIP')

pkgver() {
	cd "$srcdir/${pkgname%-VCS}"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd "$srcdir/${pkgname%-VCS}/naxos-dl-gui"
	make
}

package() {
	cd "$srcdir/${pkgname%-VCS}/naxos-dl-gui"
	make DESTDIR="$pkgdir" install
}
