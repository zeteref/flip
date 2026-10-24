pkgname=flip
pkgver=0.3.6
pkgrel=1
pkgdesc="Comic and image viewer"
arch=('any')
url="https://github.com/zeteref/flip"
license=('MIT')
depends=('electron' 'attr')

# write the built package to /tmp instead of cluttering the source dir
PKGDEST=/tmp

package() {
  install -d "$pkgdir/usr/lib/flip-electron"
  cp -r "$startdir/main.js" "$startdir/preload.js" "$startdir/renderer" "$startdir/package.json" \
    "$pkgdir/usr/lib/flip-electron/"
  install -Dm755 "$startdir/flip" "$pkgdir/usr/bin/flip"
  install -Dm644 "$startdir/config.example" "$pkgdir/usr/share/flip/config.example"
  install -Dm644 "$startdir/flip.desktop" "$pkgdir/usr/share/applications/flip.desktop"
  install -Dm644 "$startdir/flip.svg" "$pkgdir/usr/share/icons/hicolor/scalable/apps/flip.svg"
}
