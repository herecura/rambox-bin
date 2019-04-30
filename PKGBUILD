
pkgname=rambox-bin
pkgver=0.6.7
pkgrel=1
pkgdesc='messaging and emailing app that combines common web applications into one.'
arch=('x86_64')
depends=('alsa-lib' 'desktop-file-utils' 'gtk3' 'libnotify' 'libxtst' 'libxss' 'nss')
provides=("rambox")
url='http://rambox.pro/'
license=('GPL3')
source=("https://github.com/ramboxapp/community-edition/releases/download/$pkgver/Rambox-$pkgver-linux-x86_64.rpm"
)
sha512sums=('77f1556bd4d13d02f74a103dbe36941bb05fcf946519c84f65c0c12a8d36cd66fb730e7c996bcef8f20ac78bbd8a6c2a38ac44b161b071c1b039ec1de1bb92a5')

package() {
    cp -a "$srcdir"/{opt,usr} "$pkgdir"

    sed -e 's/\(Exec=\).*/\1rambox %U/' \
        -i "$pkgdir/usr/share/applications/rambox.desktop"

    install -dm755 "$pkgdir/usr/bin"
    ln -sf "/opt/Rambox/rambox" "$pkgdir/usr/bin/rambox"
}
