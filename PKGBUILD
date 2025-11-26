# Maintainer: Stephano Cetola <stephanoc@gmail.com>

pkgname=linux-mnt-pocket-headers
pkgver=6.17.9
_pkgrel=2
_kernver="${pkgver}-mnt-pocket"
pkgrel=2
pkgdesc="Header files and scripts for building modules for linux-mnt-pocket kernel"
arch=('aarch64')
url="https://github.com/cetola/linux-mnt-pocket-headers"
license=('GPL2')
depends=('perl')

source=("https://github.com/cetola/mnt-build/releases/download/${pkgver}-${pkgrel}-mnt-pocket/headers-${pkgver}-${pkgrel}-mnt.tar.gz")
sha256sums=('d2db0f9c256ec7d9716b6a907bf5e835691413bcce46e3bdcbd4af59cff749ad')

provides=("linux-headers=${pkgver}")
conflicts=('linux-aarch64-headers' 'linux-headers')
options=('!strip')

build() {
  cd "linux-${pkgver}"
}

package() {
  cd "linux-${pkgver}"
  install -dm755 "${pkgdir}/usr/lib/modules/${_kernver}/build"
  echo "Installing pre-prepared kernel headers..."
  cp -a . "${pkgdir}/usr/lib/modules/${_kernver}/build"

  rm -f  "${pkgdir}/usr/lib/modules/${_kernver}/build/Makefile.orig"
  rm -f  "${pkgdir}/usr/lib/modules/${_kernver}/build/.version"
  rm -f  "${pkgdir}/usr/lib/modules/${_kernver}/build/vmlinux"
  rm -rf "${pkgdir}/usr/lib/modules/${_kernver}/build/source"
}
