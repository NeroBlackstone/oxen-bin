# Maintainer: Nero Blackstone <gf7600gs@gmail.com>

pkgname=oxen-bin
pkgver=0.24.4
pkgrel=1
pkgdesc="Oxen CLI. Oxen is a lightning fast data version control system for structured and unstructured machine learning datasets."
arch=('x86_64')
url="https://www.oxen.ai/"
license=('Apache-2.0')
source=("https://github.com/Oxen-AI/Oxen/releases/download/v${pkgver}/oxen-ubuntu-latest.deb")
sha256sums=('12e4767d823b1ee6c6e93990ddcac137fda54dbb762742aca740cf38a096ac09')

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
