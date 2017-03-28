# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
pkgname=leiningen
pkgver=2.7.1
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

md5sums="916175bd3fe950fc5373ce27fd9e5c82  leiningen-2.7.1.tar.gz
62c420102bc49b75c2f72eb0bc3376bb  leiningen-2.7.1-standalone.jar"
sha256sums="953c95c2656c46320c88dc683202030fdd9554e8390a4b4aaaba6d019088df6f  leiningen-2.7.1.tar.gz
2ddc7e89bbb45cf1ca3d666a10dce0d3f154b77ad201aa58f430e84e71587c47  leiningen-2.7.1-standalone.jar"
sha512sums="f6f2f37624b07fde25f551433bddf64ce7fb0d4d89ee90c61eeee223e3ac18b7b923c23f45c79d7bb6e3c91adefc419cab45acce285e6007dd55046b52fa2951  leiningen-2.7.1.tar.gz
6f0ac01917b273c063dd16d8a5e98cba0265ba19766ce6a2c1e160367e3514e637c969f831384845e752cde015e1357eecac7141259e279584577f4f527bc08a  leiningen-2.7.1-standalone.jar"
