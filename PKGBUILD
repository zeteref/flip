pkgname=flip-git
_pkgname=flip
pkgver=r1.0000000
pkgrel=1
pkgdesc="Comic and image viewer"
arch=('any')
url="https://github.com/zeteref/flip"
license=('MIT')
depends=('electron' 'attr')
provides=("$_pkgname")
conflicts=("$_pkgname")
replaces=("$_pkgname")
source=("$_pkgname::git+https://github.com/zeteref/flip.git")
sha256sums=('SKIP')

pkgver() {
  cd "$_pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short=7 HEAD)"
}

package() {
  install -d "$pkgdir/usr/lib/flip-electron"
  cp -r "$_pkgname"/main.js "$_pkgname"/preload.js "$_pkgname"/renderer "$_pkgname"/package.json \
    "$pkgdir/usr/lib/flip-electron/"
  install -Dm755 "$_pkgname/$_pkgname" "$pkgdir/usr/bin/$_pkgname"
  install -Dm644 "$_pkgname/config.example" "$pkgdir/usr/share/flip/config.example"
  install -Dm644 "$_pkgname/flip.desktop" "$pkgdir/usr/share/applications/flip.desktop"
  install -Dm644 "$_pkgname/flip.svg" "$pkgdir/usr/share/icons/hicolor/scalable/apps/flip.svg"
}
