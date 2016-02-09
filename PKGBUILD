pkgname=sublime-text-dev
pkgver=3.3103
pkgrel=1
pkgdesc="Sophisticated text editor for code, html and prose - dev build"
arch=('x86_64')
url="http://www.sublimetext.com/3"
license=('custom')
depends=(libpng gtk2)
install=${pkgname}.install

source=(
  "https://download.sublimetext.com/sublime_text_3_build_${pkgver:2}_x64.tar.bz2"
  "sublime_text_3.desktop"
)
md5sums=('f047eda20cf9f8ac8760e448be12b33e'
         '89594b9c6b9a8c7e6a8ce414a0e58243')

package() {
  cd "${srcdir}"

  install -dm755 "${pkgdir}/opt"
  cp --preserve=mode -r "sublime_text_3" "${pkgdir}/opt/sublime_text_3"

  for res in 128x128 16x16 256x256 32x32 48x48; do
    install -dm755 "${pkgdir}/usr/share/icons/hicolor/${res}/apps"
    ln -s "/opt/sublime_text_3/Icon/${res}/sublime-text.png" "${pkgdir}/usr/share/icons/hicolor/${res}/apps/sublime-text.png"
  done

  install -dm755 "${pkgdir}/usr/share/applications"
  install -Dm644 "sublime_text_3.desktop" "${pkgdir}/usr/share/applications/sublime_text_3.desktop"

  install -dm755 "${pkgdir}/usr/bin"
  ln -s "/opt/sublime_text_3/sublime_text" "${pkgdir}/usr/bin/subl3"
}
