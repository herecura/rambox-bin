
pkgname=rambox-bin
pkgver=0.7.5
pkgrel=1
pkgdesc='messaging and emailing app that combines common web applications into one.'
arch=('x86_64')
depends=('alsa-lib' 'desktop-file-utils' 'gtk3' 'libnotify' 'libxtst' 'libxss' 'nss')
provides=("rambox")
url='http://rambox.pro/'
license=('GPL3')
source=("https://github.com/ramboxapp/community-edition/releases/download/$pkgver/Rambox-$pkgver-linux-x86_64.rpm"
)
sha512sums=('d1434c59adb292266a0c86b8b18b4b02eb4891c14b83b917f64b65e7a616dc550ccc768726d7a341d96c1b776a5b26d45f2080b78c762545b94bbd8b56bd9231')

package() {
    cp -a "$srcdir"/{opt,usr} "$pkgdir"

    sed -e 's/\(Exec=\).*/\1rambox %U/' \
        -i "$pkgdir/usr/share/applications/rambox.desktop"

    install -dm755 "$pkgdir/usr/bin"
    ln -sf "/opt/Rambox/rambox" "$pkgdir/usr/bin/rambox"
}
