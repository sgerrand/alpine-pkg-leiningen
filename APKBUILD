# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
pkgname=leiningen
pkgver=2.9.9
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
source="$pkgname-$pkgver.tar.gz::https://codeberg.org/$pkgname/$pkgname/archive/$pkgver.tar.gz
		$pkgname-$pkgver-standalone.jar::https://codeberg.org/$pkgname/$pkgname/releases/download/$pkgver/$pkgname-$pkgver-standalone.jar"

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

sha512sums="
a844d9637116219e839a129e3a953ba8fcc0f94abab0f2e95cde235a736a24337aadc6672ee0d558b9e307f9684515127a6c96155e314d5bf004763e36a85f4d  leiningen-2.9.9.tar.gz
09dca49c24315e38b963e6ac426246234ad15757cf1a66672bf1cb0f2f047815cbb477390868e8286c3c9252a6133f980c744a37ef6e431c2414f5109ea4342f  leiningen-2.9.9-standalone.jar
"
