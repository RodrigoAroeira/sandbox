pkgname="xdg-sandbox"
pkgver="0.1.0"
pkgrel=2
arch=('any')
source=('sandbox')
md5sums=('61aebb24064e82ed137f02c08f900956')
depends=('bash')

verify() {
  bash -n sandbox
}

package() {
  local name
  case "${INSTALL_AS_SANDBOX,,}" in
  1 | true | yes | y)
    name="sandbox"
    ;;
  *)
    name="$pkgname"
    ;;
  esac
  install -Dm755 sandbox "$pkgdir/usr/bin/$name"
}
