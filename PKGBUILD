# Maintainer: Shuta4 <shuta4@proton.me>

_pkgname=dwmblocks
pkgname="s4-$_pkgname"
pkgver=1.1
pkgrel=1
pkgdesc="A modular statusbar for dwm custom build"
url="https://github.com/Shuta4/dwmblocks"
arch=('i686' 'x86_64' 'arm' 'armv7h' 'armv6h' 'aarch64')
license=('MIT')
options=(zipman)
depends=('libx11')
source=("https://github.com/Shuta4/$_pkgname/archive/refs/tags/$pkgver-$pkgrel.tar.gz")
sha256sums=('4f7cb870dd9588c3c10d8821b40ee80bed3e49705605b031293df4592ee3b1e6')

provides=("${_pkgname}")
conflicts=("${_pkgname}")

build() {
  cd "$srcdir/$_pkgname-$pkgver-$pkgrel"
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  cd "$srcdir/$_pkgname-$pkgver-$pkgrel"
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$_pkgname/LICENSE"
  install -Dm644 README.md "$pkgdir/usr/share/doc/$_pkgname/README.md"
}
