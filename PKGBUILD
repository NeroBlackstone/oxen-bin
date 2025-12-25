# Maintainer: Nero Blackstone <gf7600gs@gmail.com>

pkgname=oxen-bin
pkgver=0.42.2
pkgrel=1
pkgdesc="Oxen CLI. Oxen is a lightning fast data version control system for structured and unstructured machine learning datasets."
arch=('x86_64')
url="https://www.oxen.ai/"
license=('Apache-2.0')
source=("https://github.com/Oxen-AI/Oxen/releases/download/v${pkgver}/oxen-linux-x86_64.deb")
sha256sums=('6164e6909d7b3282ff961a2ae0b6340f7e917a8473ff42c01f1968c85784a61a')

prepare() {
    cd "$srcdir"
    ar x oxen-linux-x86_64.deb
    tar -xf data.tar.*
    tar -xf control.tar.* || true
    find . -type d -exec chmod 755 {} +
    find . -type f -exec chmod 644 {} +
    chmod 755 usr/bin/* 2>/dev/null || true
    chmod 755 usr/sbin/* 2>/dev/null || true
}

package() {
    cd "$srcdir"
    cp -r * "$pkgdir/"
}