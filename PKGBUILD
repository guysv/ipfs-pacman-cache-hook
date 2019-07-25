# Maintainer: Guy Sviry <sviryguy@gmail.com>

pkgname=ipfs-pacman-cache-hook
pkgver=1alpha
pkgrel=1
pkgdesc="Pacman hook to upgrade systemd-boot after systemd upgrade."
arch=("any")
license=("GPL")
depends=(systemd expac pacman grep)
source=(cache-to-ipfs
    install-inotify.hook
    ipfs-pacman-cache.path
    ipfs-pacman-cache.service)
md5sums=('53d21565ba5b14f208526a5b289d8703'
         'c08be9f5db56adbc2d591fd5be09e81f'
         'b735234abca5e49900087c2fba65c357'
         'a21352465c403063cc504b443067652d')

package() {
    install -m755 -d "${pkgdir}/usr/share/libalpm/hooks"
    install -m644 "${srcdir}/install-inotify.hook" "${pkgdir}/usr/share/libalpm/hooks/install-inotify.hook"
    
    install -Dm755 "${srcdir}/cache-to-ipfs" "${pkgdir}/usr/bin/cache-to-ipfs"

    install -m755 -d "${pkgdir}/usr/lib/systemd/user"
    install -m644 "${srcdir}/ipfs-pacman-cache.path" "${pkgdir}/usr/lib/systemd/user/ipfs-pacman-cache.path"
    install -m644 "${srcdir}/ipfs-pacman-cache.service" "${pkgdir}/usr/lib/systemd/user/ipfs-pacman-cache.service"
}
