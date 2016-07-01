# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
pkgname=leiningen
pkgver=2.6.1
pkgrel=0
pkgdesc="Automate Clojure projects without setting your hair on fire."
url="https://leiningen.org"
arch="noarch"
license="Eclipse Public License"
depends="openjdk8-jre-base"
depends_dev=""
makedepends="$depends_dev openjdk8"
install=""
subpackages="$pkgname-doc"
source="$pkgname-$pkgver.tar.gz::https://github.com/technomancy/$pkgname/archive/$pkgver.tar.gz
		$pkgname-$pkgver-standalone.jar::https://github.com/technomancy/$pkgname/releases/download/2.6.1/$pkgname-$pkgver-standalone.zip"

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

md5sums="9b431769e3230fd5cc2e3434df359971  leiningen-2.6.1.tar.gz
a063df8011cc3e9151f155d9c1d4554a  leiningen-2.6.1-standalone.jar"
sha256sums="9e6a6c7b6e032921a37d5be8fcdc2c0288d3698f759e22bdd29de4eb327ebeab  leiningen-2.6.1.tar.gz
d70078fba85d5f405d042a6d7bad3a1e5b4aafae565c2d581feb999e95ae6394  leiningen-2.6.1-standalone.jar"
sha512sums="20fea59b32ca008f30f897387257e378223a25c297af15526fe7d4eac0268d11b82dc94d3bc178266e3e396de1d03a323c9b579b2ba2ebb5bfad1ad5fb03e095  leiningen-2.6.1.tar.gz
ec1a67976862987b72347bddb8f1e368ff0f01ef15d369f9af4f6184d0a9d4c98f47b8be968baab5d03c8571d7ad278097d044a41fe493f1e0169314bb96eb73  leiningen-2.6.1-standalone.jar"
