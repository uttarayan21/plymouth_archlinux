# Maintainer: Uttarayan Mondal

pkgname=plymouth-theme-archmac
_pkgname=plymouth-theme-archmac
pkgver=3.r6313793
pkgrel=1
epoch=1
pkgdesc="Mac like boot theme with Archlinux logo for plymouth"
url='https://github.com/uttarayan21/plymouth-theme-archmac'
arch=('i686' 'x86_64')
license=('MIT')
options=('zipman')
depends=('libxft')
makedepends=( 'libxext' 'git')
optdepends=()
source=('git://github.com/uttarayan21/plymouth-theme-archmac')
sha1sums=('SKIP')

provides=("${_pkgname}")
conflicts=("${_pkgname}")

pkgver() {
	cd "${_pkgname}"
	printf "%s.r%s" \
		"$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
	cd $srcdir/${_pkgname}
}

build() {
	cd "${_pkgname}"
}

package() {
	cd "${_pkgname}"
    _themedir="${pkgdir}/usr/share/plymouth/themes/archmac"
	install -Dm644 archmac.plymouth "${_themedir}/archmac.plymouth"
    install -Dm644 archmac.script   "${_themedir}/archmac.script"
    install -Ddm755 images           "${_themedir}/images"
    for image in images/*.png; do 
        install -Dm644 "${image}"   "${_themedir}/${image}"
    done

}
