# Maintainer: Ingo Gottwald <in dot gottwald at gmail dot com>
# Contributor : speps <speps at aur dot archlinux dot org>
# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=python2-sipsimple
pkgver=2.4.0
pkgrel=1
pkgdesc="Python SDK for development of SIP end-points"
license=('custom:MIT' 'LGPL')
arch=('i686' 'x86_64')
url="http://download.ag-projects.com/SipClient"
depends=('alsa-lib' 'util-linux' 'python2-dateutil'
         'python2-dnspython' 'python2-eventlib' 'python2-msrplib' 'python2-xcaplib' 'python2-application')
makedepends=('cython2' 'subversion')
options=('!makeflags')
source=("http://download.ag-projects.com/SipClient/python-sipsimple-$pkgver.tar.gz")
sha256sums=('f66543c680f22aa3cf86f55373a01a2bb699366a1be5e257c417d018696b6840')

build() {
  cd "$srcdir/python-sipsimple-$pkgver"
  python2 setup.py build_ext --pjsip-clean-compile
}

package() {
  cd "$srcdir/python-sipsimple-$pkgver"
  python2 setup.py install --root="$pkgdir" --optimize=1

  # license
  install -Dm644 LICENSE \
    "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
