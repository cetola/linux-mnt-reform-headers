# Maintainer: Stephano Cetola <stephanoc@gmail.com>

pkgname=linux-mnt-pocket-headers
pkgver=6.17.12
_pkgrel=1
_kernver="${pkgver}-mnt-pocket"
pkgrel=1
pkgdesc="Header files and scripts for building modules for linux-mnt-pocket kernel"
arch=('aarch64')
url="https://github.com/cetola/linux-mnt-pocket-headers"
license=('GPL2')
depends=('perl')

source=("https://github.com/cetola/mnt-build/releases/download/${pkgver}-${pkgrel}-mnt-pocket/headers-${pkgver}-${pkgrel}-mnt.tar.gz")
sha256sums=('96cd52e8b4e270dc80e583d58f526c9d37ede4cff9842d9078f54b0d7cce6b20')

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
