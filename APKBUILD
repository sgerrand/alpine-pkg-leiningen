# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
pkgname=leiningen
pkgver=2.8.3
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

sha512sums="77884bb3613316bc0bd9e47a16ac862b4ca102a7031a42f895966e2bb4cf660fec4aa0bc7cf2999cc105d67ca03cef4cac259c31e277c937feebf69acc6de875  leiningen-2.8.3.tar.gz
f9ed3604dbf0498524b3a137a872576de7cb5b8df6d4841cf6d552adc0b8cf2186244805cd53228d57c4285803069ed8a67a8dd33a326369cb468dcc773444f7  leiningen-2.8.3-standalone.jar"
