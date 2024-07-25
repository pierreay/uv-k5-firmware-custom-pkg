# Maintainer: Pierre Ayoub <pierre.ayoub.pro@protonmail.com>

# TODO: Add an option to disable "MESSENGER*" and "ENCRYPTION" to free 10% of
# space.

pkgname=uv-k5-firmware-custom
pkgver=0.1
pkgrel=1
pkgdesc="Custom configuration for uv-k5-firmware-custom"
arch=("any")
url="https://github.com/kamilsss655/uv-k5-firmware-custom/"
license=('GPL')
depends=("python-crcmod")
makedepends=()
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
source=("${pkgname}::git+https://github.com/kamilsss655/uv-k5-firmware-custom/"
        "0001-Fix-CHIRP-compatibility.patch"
        "0002-Enable-DTMF-1750Hz-TX.patch"
        "0003-Enable-BYPASS-and-RAW-demods.patch")
noextract=()
sha256sums=("SKIP"
            "ef8c23df75c303dc4e83d9e0a5f5d289c80737bd8daccc37bc208c8e30cbb271"
            "7f97b6631700a0b589a7ea364a7a788d607f216fb989dd9470b1f572565419e6"
            "8ae5961c1696ef21ca8cb882ee27276e05ddd3937b9bd01bf2b39ad1aa11f89f")
validpgpkeys=()

prepare() {
    cd "${pkgname}"
    patch -p1 -i "${srcdir}/0001-Fix-CHIRP-compatibility.patch"
    patch -p1 -i "${srcdir}/0002-Enable-DTMF-1750Hz-TX.patch"
    patch -p1 -i "${srcdir}/0003-Enable-BYPASS-and-RAW-demods.patch"
}

build() {
    cd "${pkgname}"
    make
}

package() {
    cd "${pkgname}"
    cp firmware.packed.bin "${pkgdir}/"
    echo "*** Open firmware flasher web interface at:"
    echo "*** https://kamilsss655.github.io/uvtools/"
    echo "*** And flash the 'firmware.packed.bin' file."
    echo "*** Flashing instructions:"
    echo "*** https://github.com/kamilsss655/uv-k5-firmware-custom/wiki/60-%E2%80%90-Flashing-the-firmware"
}
