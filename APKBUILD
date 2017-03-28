# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
pkgname=leiningen
pkgver=2.7.0
pkgrel=0
pkgdesc="Automate Clojure projects without setting your hair on fire."
url="https://leiningen.org"
arch="noarch"
license="Eclipse Public License"
depends="bash openjdk8-jre-base"
depends_dev=""
makedepends="$depends_dev openjdk8"
install=""
subpackages="$pkgname-doc"
source="$pkgname-$pkgver.tar.gz::https://github.com/technomancy/$pkgname/archive/$pkgver.tar.gz
		$pkgname-$pkgver-standalone.jar::https://github.com/technomancy/$pkgname/releases/download/$pkgver/$pkgname-$pkgver-standalone.zip"

_builddir="$srcdir"/leiningen-$pkgver
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
}

package() {
	cd "$_builddir"
	install -Dm755 "$srcdir"/$pkgname-$pkgver-standalone.jar "$pkgdir"/usr/share/java/$pkgname-$pkgver-standalone.jar
	install -Dm755 bin/lein-pkg "$pkgdir"/usr/bin/lein
	mkdir -p "$pkgdir"/usr/share/doc/$pkgname
	install -Dm644 *.md "$pkgdir"/usr/share/doc/$pkgname
	install -Dm644 doc/*.md "$pkgdir"/usr/share/doc/$pkgname
	install -Dm644 COPYING "$pkgdir"/usr/share/licenses/$pkgname/COPYING
}

md5sums="122ea6e5fbe8d09741eb564920649be4  leiningen-2.7.0.tar.gz
ae33517c5bce56f6e36f863bcc42cbea  leiningen-2.7.0-standalone.jar"
sha256sums="db2069e9a87c72c7f83934e3068dc4b28c688115f7869056c4150392abc54c3d  leiningen-2.7.0.tar.gz
b0a53fd9fa73e9d87c04ef25ba1ca174b0c062b803108648d7157176ccde7435  leiningen-2.7.0-standalone.jar"
sha512sums="f5de842f24ad4bbbef66c228d4de08c351ec893464a4f70cf16cd62e11fb300ddc715945a4dec12912008df812ad1bc2b7d7fa66ca0f3f35d7125c7dead6c990  leiningen-2.7.0.tar.gz
d42288c696d5b4d86c41a0ca9b8e748cdb9200c3adc23161b9b97b8c2f3da9c5bd811e2ddae265bf11d323b1449291e9914bf1e222aaf403e73ceef4084ed082  leiningen-2.7.0-standalone.jar"
