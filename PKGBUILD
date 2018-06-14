
pkgname=rambox-bin
_pkgname=rambox
pkgver=0.5.17
pkgrel=1
pkgdesc='messaging and emailing app that combines common web applications into one.'
arch=('x86_64')
depends=('alsa-lib' 'bash' 'desktop-file-utils' 'gconf' 'gtk2' 'libnotify' 'libxtst' 'libxss' 'nss')
provides=("rambox")
url='http://rambox.pro/'
license=('GPL3')
source=("https://github.com/saenzramiro/rambox/releases/download/$pkgver/rambox-$pkgver-x64.tar.gz"
        "${_pkgname}.sh"
        "${_pkgname}.desktop"
        "${_pkgname}.png"
)
sha512sums=('66410ecb9a80fb461e6d6f42ffb2b999679f974a5fcf79343fc4f381616e26cff8fb296efffffe4adb6fdf101f5f3f57f38ccb4404d8b132355ed8c022531b46'
            '4b6febec72a3f882754a411651f07eb545921a4983827341dcb495d210db6d88c557ab7183267399ac3d1b09887f0b873cd9829d14dc72fec63757d04f9d2b71'
            '0ef350ab5295c01f8895f227a4bd43ad1c91c73add80ee5489e66e96b4d3810e1bd477f0345e3e3db46295446253a84fdb20458242e612e58503d9abc3f05204'
            '13958fb17ecf35b0766a20b1b3d7b1f69658778ecbc58169ebb3b33c67bf9251d398a85afb6d2266bfe787cead73049d03d900162a963520afd6af7a2b83b34f')

package() {
    install -d ${pkgdir}/{opt/rambox,usr/{bin,share/pixmaps}}
    cp -R ${srcdir}/Rambox-${pkgver}/* ${pkgdir}/opt/${_pkgname}/
    install -Dm755 $srcdir/${_pkgname}.sh ${pkgdir}/usr/bin/${_pkgname}
    install -Dm644 $srcdir/${_pkgname}.png ${pkgdir}/usr/share/pixmaps/${_pkgname}.png
    desktop-file-install ${srcdir}/${_pkgname}.desktop --dir ${pkgdir}/usr/share/applications/
}
