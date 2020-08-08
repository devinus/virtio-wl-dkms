# Maintainer: Devin Alexander Torres <d@devinus.io>

_pkgbase=virtio_wl
pkgname=virtio_wl-dkms-git
pkgver=1
pkgrel=1
pkgdesc="The virtio-wl kernel driver (DKMS)"
arch=('i686' 'x86_64')
url="https://github.com/devinus/virtio-wl-dkms"
license=('GPL2')
depends=('dkms')
makedepends=('git')
conflicts=("${_pkgbase}")
source=("${_pkgbase}::git+https://github.com/devinus/virtio-wl-dkms.git")
md5sums=('SKIP')

package() {
  cd "${srcdir}/${_pkgbase}"
  install -Dm644 dkms.conf "${pkgdir}/usr/src/${_pkgbase}-${pkgver}/dkms.conf"
  install -Dm644 Makefile "$pkgdir/usr/src/${_pkgbase}-${pkgver}/Makefile"
  install -Dm644 virtio_drm.h "$pkgdir/usr/src/${_pkgbase}-${pkgver}/virtio_drm.h"
  install -Dm644 virtio_wl.c "$pkgdir/usr/src/${_pkgbase}-${pkgver}/virtio_wl.c"
	install -Dm644 virtio_wl.h "$pkgdir/usr/src/${_pkgbase}-${pkgver}/virtio_wl.h"
  install -Dm644 virtwl.h "$pkgdir/usr/src/${_pkgbase}-${pkgver}/virtwl.h"
  sed -e "s/@_PKGBASE@/${_pkgbase}/" \
      -e "s/@PKGVER@/${pkgver}/" \
      -i "${pkgdir}/usr/src/${_pkgbase}-${pkgver}/dkms.conf"
}
