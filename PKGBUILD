# vim:set ft=sh et:
# Maintainer : BlackEagle < ike DOT devolder AT gmail DOT com >

_pkgname=tuxedo-cc-wmi
pkgname=$_pkgname-bede
pkgver=0.1.4
_current_linux_version=5.7.13
_next_linux_version=5.8
pkgrel=6
pkgdesc="WMI method control for TUXEDO laptops for linux-bede"
arch=('x86_64')
url="https://github.com/tuxedocomputers/tuxedo-cc-wmi"
makedepends=(
    "linux-bede>=$_current_linux_version"
    "linux-bede-headers>=$_current_linux_version"
    "linux-bede<$_next_linux_version"
    "linux-bede-headers<$_next_linux_version"
    "tuxedo-cc-wmi-dkms=$pkgver"
)
provides=('tuxedo-cc-wmi')
license=('GPL3')
source=()

package() {
	depends=(
        "linux-bede>=$_current_linux_version"
        "linux-bede<$_next_linux_version"
    )

    local kernver=$(</usr/src/linux-bede/version)
    local extradir="/usr/lib/modules/$kernver/extramodules"
    install -dm755 "${pkgdir}${extradir}/$_pkgname"
    cp -a "/var/lib/dkms/$_pkgname/kernel-$kernver-x86_64/module"/* \
        "${pkgdir}${extradir}/$_pkgname/"
}








