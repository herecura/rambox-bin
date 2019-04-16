
pkgname=rambox-bin
pkgver=0.6.6
pkgrel=1
pkgdesc='messaging and emailing app that combines common web applications into one.'
arch=('x86_64')
depends=('alsa-lib' 'desktop-file-utils' 'gtk3' 'libnotify' 'libxtst' 'libxss' 'nss')
provides=("rambox")
url='http://rambox.pro/'
license=('GPL3')
source=("https://github.com/ramboxapp/community-edition/releases/download/$pkgver/Rambox-$pkgver-linux-x86_64.rpm"
)
sha512sums=('4fac556e7f4ced5f97244caf8dc718b6e113e38863aec568f589f246f57303f90c028255dfb78c50e800faa6b4723bff4d498ac5b1509bec2bd906233482df44')

package() {
    cp -a "$srcdir"/{opt,usr} "$pkgdir"

    sed -e 's/\(Exec=\).*/\1rambox %U/' \
        -i "$pkgdir/usr/share/applications/rambox.desktop"

    install -dm755 "$pkgdir/usr/bin"
    ln -sf "/opt/Rambox/rambox" "$pkgdir/usr/bin/rambox"
}
