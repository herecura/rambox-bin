
pkgname=rambox-bin
pkgver=0.6.3
pkgrel=1
pkgdesc='messaging and emailing app that combines common web applications into one.'
arch=('x86_64')
depends=('alsa-lib' 'desktop-file-utils' 'gtk3' 'libnotify' 'libxtst' 'libxss' 'nss')
provides=("rambox")
url='http://rambox.pro/'
license=('GPL3')
source=("https://github.com/ramboxapp/community-edition/releases/download/$pkgver/Rambox-$pkgver-linux-x86_64.rpm"
)
sha512sums=('a210b8559336b98f0ef181d3470c868cd655b36aaaefa2135d23e168f807f1a5293ec8e1e01352754e0ae4ceafdda5bd90fb920484c175092d4dbcbd9a130317')

package() {
    cp -a "$srcdir"/{opt,usr} "$pkgdir"

    sed -e 's/\(Exec=\).*/\1rambox %U/' \
        -i "$pkgdir/usr/share/applications/rambox.desktop"

    install -dm755 "$pkgdir/usr/bin"
    ln -sf "/opt/Rambox/rambox" "$pkgdir/usr/bin/rambox"
}
