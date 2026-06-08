pkgname="xdg-sandbox"
pkgver=0.3.0
pkgrel=1
arch=('any')
source=('sandbox')
md5sums=('b251346e8f40c7472ee57322736ed245')
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
