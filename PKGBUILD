pkgname="sandbox"
pkgver="0.1.0"
pkgrel=1
arch=('any')
source=('sandbox')
md5sums=("61aebb24064e82ed137f02c08f900956")
depends=('bash')

verify() {
  bash -n sandbox
}

package() {
  install -Dm755 sandbox "$pkgdir/usr/bin/sandbox"
}
