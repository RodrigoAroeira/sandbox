pkgname="xdg-sandbox"
pkgver=0.3.0
pkgrel=1
arch=('any')
source=('sandbox')
md5sums=('1210ebf5e8305f48bbcd60299a8911b2')
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
