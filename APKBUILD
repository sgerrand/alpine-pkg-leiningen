# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
pkgname=leiningen
pkgver=2.9.7
pkgrel=0
pkgdesc="Automate Clojure projects without setting your hair on fire."
url="https://leiningen.org"
arch="noarch"
license="Eclipse Public License"
depends="bash openjdk11-jre-headless"
depends_dev=""
makedepends="$depends_dev openjdk11"
install=""
subpackages="$pkgname-doc"
source="$pkgname-$pkgver.tar.gz::https://github.com/technomancy/$pkgname/archive/$pkgver.tar.gz
		$pkgname-$pkgver-standalone.jar::https://github.com/technomancy/$pkgname/releases/download/$pkgver/$pkgname-$pkgver-standalone.jar"

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

sha512sums="a8ed011387e5d2cd5b2d4e426b934cbb61a4d3e728d0d4af5e71141915f8a452c59dd72d35a30036e9a5f223e8bc40a6e43ae3b9cceb14f5e1030fd0f48fcd40  leiningen-2.9.7.tar.gz
35924ab5a93b3408c02f13b8904275aad81382656c1be0bf3f0b4f47e0b805bcb1f778fbf2e0a894319675e57fdb54f0e5500bec03d18f959450ddfca5267515  leiningen-2.9.7-standalone.jar"
