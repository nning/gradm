# Contributors:
#   Jonathan Liu <net147@gmail.com>
#   henning mueller <henning@orgizm.net>
#   s1gma, Ahmad24, maxrp
#
# Find this package in the AUR:
#   https://aur.archlinux.org/packages/gradm
#
# Please report bugs and feature requests on GitHub:
#   https://github.com/nning/gradm
#

pkgname=gradm
pkgver=3.0
_timestamp=201401291757
pkgrel=3
pkgdesc='Administrative interface for the grsecurity Role Based Access Control system'
arch=(i686 x86_64)
url=http://grsecurity.net/
license=(GPL2)
depends=(pam)
source=(
  http://grsecurity.net/stable/$pkgname-$pkgver-$_timestamp.tar.gz
  learn_config
  policy
)

build() {
  cd "$srcdir/$pkgname"
  sed -i -e 's/^CFLAGS :=/CFLAGS +=/' -e 's:sbin:usr/bin:' Makefile
  make
}

package() {
  cd "$srcdir/$pkgname"
  make DESTDIR="$pkgdir" install
  cp "$startdir"/{learn_config,policy} "$pkgdir/etc/grsec"
  rm -rf "$pkgdir/dev"
}

sha256sums=('9c99714e6d10797a7348c6ffe2561dfcfe5e7659c9d86118d381b8bdb09ae7a6'
            'ec8e824e8a29a67be76bf853814ee85e80c4063009e5693d5db8cdb45bd45813'
            '61c0e84098e8386e5496dafce559558adef32e2a4a1241a9fa3bd56eab192dcd')
