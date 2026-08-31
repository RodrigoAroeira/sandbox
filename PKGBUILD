pkgname="xdg-sandbox"
pkgver=0.3.1
pkgrel=1
arch=('any')
source=('sandbox')
md5sums=('1f7251e8f41ce7862e0c947e06844738')
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
