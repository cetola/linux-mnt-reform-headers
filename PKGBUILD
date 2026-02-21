# Maintainer: Stephano Cetola <stephanoc@gmail.com>

pkgname=linux-mnt-reform-headers
pkgver=6.18.13
_pkgrel=1
_kernver="${pkgver}-mnt-reform"
pkgrel=1
pkgdesc="Header files and scripts for building modules for linux-mnt-reform kernel"
arch=('aarch64')
url="https://github.com/cetola/linux-mnt-reform-headers"
license=('GPL2')
depends=('perl')

source=("https://github.com/cetola/mnt-build/releases/download/${pkgver}-${pkgrel}-mnt-reform/headers-${pkgver}-${pkgrel}-mnt.tar.gz")
sha256sums=('079db00a04d9d2ae9573583bc5fd8e84b12fa8cd18c8cb3f0dad74c42878ee8d')

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
