# Maintainer: Nero Blackstone <gf7600gs@gmail.com>

pkgname=oxen-bin
pkgver=0.33.1
pkgrel=1
pkgdesc="Oxen CLI. Oxen is a lightning fast data version control system for structured and unstructured machine learning datasets."
arch=('x86_64')
url="https://www.oxen.ai/"
license=('Apache-2.0')
source=("https://github.com/Oxen-AI/Oxen/releases/download/v${pkgver}/oxen-ubuntu-latest.deb")
sha256sums=('e9bb473339fd0bae02356b12ebec46d5c9a81cb992fea6d761693345d04ce37a')

prepare() {
    mkdir -p "$srcdir/$pkgname-$pkgver"
    cd "$srcdir/$pkgname-$pkgver"
    ar x "$srcdir/oxen-ubuntu-latest.deb"
    tar --use-compress-program=unzstd -xvf data.tar.gz
}

package() {
    cd "$srcdir/$pkgname-$pkgver"
    
    install -dm755 "$pkgdir/usr/bin"
    cp -r usr/bin/* "$pkgdir/usr/bin/"
    
    install -dm755 "$pkgdir/usr/share"
    cp -r usr/share/* "$pkgdir/usr/share/"
}
