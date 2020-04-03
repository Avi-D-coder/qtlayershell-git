pkgname=qtlayershell-git
pkgname_=qtlayershell
pkgver=9696838
pkgrel=1
pkgdesc='Qt support for the Wayland layer-shell extension'
arch=('any')
url='https://neovim.io'
license=('MIT')
depends=()
makedepends=('git' 'meson' 'ninja')

source=("git+https://github.com/ddevault/qtlayershell.git")
sha256sums=('SKIP')
provides=("qtlayershell")
conflicts=('qtlayershell')

pkgver() {
  cd "${pkgname_}"
  git rev-parse --short HEAD
}

build() {
  cd "${pkgname_}"
  meson build --prefix /usr
  ninja -C build
}

package() {
  cd "${pkgname_}"
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname_}/LICENSE"
  DESTDIR="$pkgdir" ninja install
}

# vim:set sw=2 sts=2 et:
