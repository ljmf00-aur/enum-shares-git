# Maintainer: Luís Ferreira <contact@lsferreira.net>
# Contributor: Levon 'noptrix' Kayan <noptrix@nullsecurity.net>

# This file is part of BlackArch Linux ( http://blackarch.org ).
# See COPYING for license details.

pkgname='enum-shares-git'
pkgver='7.97cba5a'
pkgrel=2
pkgdesc='Tool that enumerates shared folders across the network and under a custom user account.'
groups=('blackarch' 'blackarch-scanner')
arch=('any')
url='https://github.com/dejanlevaja/enum_shares'
license=('GPL2')
depends=('python2' 'python2-pysmb')
makedepends=('git')
source=('git+https://github.com/dejanlevaja/enum_shares.git')
sha1sums=('SKIP')
provides=('enum-shares')
conflicts=('enum-shares')

pkgver() {
  cd "$srcdir/enum_shares"

  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

prepare() {
  cd "$srcdir/enum_shares"

  sed -i 's|/usr/bin/env python|/usr/bin/env python2|g' enum_shares.py
}

package() {
  cd "$srcdir/enum_shares"

  install -Dm755 enum_shares.py "$pkgdir/usr/bin/enum-shares"
  install -Dm644 README.md "$pkgdir/usr/share/doc/enum-shares/README.md"
  install -Dm644 LICENSE.md "$pkgdir/usr/share/licenses/enum-shares/LICENSE.md"
}

