# Contributor: randomdev 
# Maintainer: randomdev 
pkgname=libecap
pkgver=0.2.0
pkgrel=0
pkgdesc="eCAP libary to us with an HTTP proxy or an ICAP server, to outsource content analysis and adaptation to a loadable module."
url="http://www.e-cap.org/"
arch="all"
license="BSD"
depends=""
depends_dev=""
makedepends="$depends_dev"
install=""
subpackages=""
source="http://www.measurement-factory.com/tmp/ecap/$pkgname-$pkgver.tar.gz"

_builddir="$srcdir"/$pkgname-$pkgver
prepare() {
	local i
	cd "$_builddir"
	for i in $source; do
		case $i in
		*.patch) msg $i; patch -p1 -i "$srcdir"/$i || return 1;;
		esac
	done
}

build() {
	cd "$_builddir"
	./configure \
		--prefix=/usr \
		|| return 1
	make || return 1
}

package() {
	cd "$_builddir"
	make DESTDIR="$pkgdir" install || return 1

	rm "$pkgdir"/usr/lib/*.la
	
}

md5sums="e65a855f4fbb0f3136af7fe28249e883  libecap-0.2.0.tar.gz"
sha256sums="19e195d60cf67ec3b49fe4d109823d753546b5da115230499ad1a9cb65ca92d2  libecap-0.2.0.tar.gz"
sha512sums="5d39444ec79846b14a7f4292e51bb880befd2cbf581b257d5087517cfae1dce55e4439a90c08e0b8f5b3e8b2431dde8c6fab771c826489024f17625cfc8c777e  libecap-0.2.0.tar.gz"
