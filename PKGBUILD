pkgname="xdg-sandbox"
pkgver="0.2.0"
pkgrel=1
arch=('any')
source=('sandbox')
md5sums=('f5eeb978c8d02697dfc3909eed6b59e3')
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
