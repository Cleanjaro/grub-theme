# Maintainer: Philip Müller <philm[at]manjaro[dog]org>
# Contributor: artoo <artoo@manjaro.org>
# Contributor: anex <assassin.anex[@]gmail.com>
# Contributor: Stefano Capitani <stefano@manjaro.org>
# Contributor: Matti Hyttinen <matti@manjaro.org> 


pkgbase=grub-theme-live
pkgname=('grub-theme-live-common' 'grub-theme-live-cleanjaro' 'grub-theme-cleanjaro')
pkgver=19.10
pkgrel=1
pkgdesc='Cleanjaro Linux grub theme'
arch=('any')
url="https://github.com/Yorper/grub-theme"
license=('GPL')
makedepends=('git')
source=("grub-theme::git+$url.git")
sha256sums=('SKIP')

package_grub-theme-live-common() {
    depends=('grub')
    conflicts=('grub-theme-live')
    replaces=('grub-theme-live')

    cd grub-theme
    make PREFIX=/usr DESTDIR=${pkgdir} install_common
}
package_grub-theme-live-cleanjaro() {
    depends=('grub-theme-live-common')

    cd grub-theme
    make PREFIX=/usr DESTDIR=${pkgdir} install_manjaro
}

package_grub-theme-cleanjaro() {
	depends=('grub')
	install=cleanjaro-theme.install
    
    cd grub-theme/cleanjaro-live
    sed -i -e 's,.*text = "Welcome to Cleanjaro".*,#text = "Welcome to Cleanjaro",' theme.txt #remove welcome message
    find . -type f -exec install -D -m644 {} ${pkgdir}/usr/share/grub/themes/cleanjaro/{} \;
}



