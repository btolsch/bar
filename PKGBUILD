# Maintainer: Brandon Tolsch <btolsch@gmail.com>
pkgname=lemonbar-xft-xbm-git
_pkgname=bar
pkgver=270.08aae79
pkgrel=1
pkgdesc="A lightweight xcb based bar with ported xft and xbm support."
arch=('i686' 'x86_64')
url="https://github.com/btolsch/bar"
license=('MIT')
depends=('libxcb' 'libxft' 'libx11')
makedepends=('git')
provides=('bar-aint-recursive' 'lemonbar')
conflicts=('bar-aint-recursive' 'lemonbar')
source=("$_pkgname::git+https://github.com/btolsch/bar.git#branch=xft-xbm")
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/$_pkgname"
  echo $(git rev-list --count xft-xbm).$(git rev-parse --short xft-xbm)
}

build() {
  cd "$srcdir/$_pkgname"
  make
}

package() {
  cd "$srcdir/$_pkgname"
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -D -m644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
