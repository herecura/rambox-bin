
pkgname=rambox-bin
pkgver=0.6.1
pkgrel=1
pkgdesc='messaging and emailing app that combines common web applications into one.'
arch=('x86_64')
depends=('alsa-lib' 'desktop-file-utils' 'gtk3' 'libnotify' 'libxtst' 'libxss' 'nss')
provides=("rambox")
url='http://rambox.pro/'
license=('GPL3')
source=("https://github.com/ramboxapp/community-edition/releases/download/$pkgver/Rambox-$pkgver-linux-x86_64.rpm"
)
sha512sums=('30f9098ee51184ecc5e66c225d0e28fd8c0e924d7744b5c8cac003a75fdec728f56255514b80fac8bf3df3118cab8d338add6808d4714056570a25c4db471a47')

package() {
    cp -a "$srcdir"/{opt,usr} "$pkgdir"

    sed -e 's/\(Exec=\).*/\1rambox %U/' \
        -i "$pkgdir/usr/share/applications/rambox.desktop"

    install -dm755 "$pkgdir/usr/bin"
    ln -sf "/opt/Rambox/rambox" "$pkgdir/usr/bin/rambox"
}
