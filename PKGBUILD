# Maintainer: Stephano Cetola <stephanoc@gmail.com>

pkgname=linux-mnt-reform-headers
pkgver=6.18.10
_pkgrel=1
_kernver="${pkgver}-mnt-reform"
pkgrel=1
pkgdesc="Header files and scripts for building modules for linux-mnt-reform kernel"
arch=('aarch64')
url="https://github.com/cetola/linux-mnt-reform-headers"
license=('GPL2')
depends=('perl')

source=("https://github.com/cetola/mnt-build/releases/download/${pkgver}-${pkgrel}-mnt-reform/headers-${pkgver}-${pkgrel}-mnt.tar.gz")
sha256sums=('6e3ee6ba04ca860c3d978fab6ca4692499e390c005e8a26271c7f6c04788d96f')

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
}
