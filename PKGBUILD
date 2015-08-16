# Maintainer: SpepS <dreamspepser at yahoo dot it>

pkgname=lv2-dynmanifest
pkgver=1.2
pkgrel=2
pkgdesc="Lv2 Dynamic Manifest extension"
arch=(any)
url="http://lv2plug.in/"
license=('custom:ISC')
groups=('lv2-extensions')
depends=('lv2core>=6.0')
provides=('lv2-dyn-manifest')
conflicts=('lv2-dyn-manifest')
replaces=('lv2-dyn-manifest')
source=("$url/spec/$pkgname-$pkgver.tar.bz2")
md5sums=('5c4e4b9a717dbbb253602a137fda910d')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  python2 waf configure --prefix=/usr
  python2 waf build
}

package() {
  cd "$srcdir/$pkgname-$pkgver"

  python2 waf install --destdir="$pkgdir/"

  # license
  install -d "$pkgdir/usr/share/licenses/$pkgname"
  head -n 15 ${pkgname/lv2-}.ttl > \
    "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

# vim:set ts=2 sw=2 et:
