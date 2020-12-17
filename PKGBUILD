# ##############################################################################################
#
# PKGBUILD based on https://aur.archlinux.org/cgit/aur.git/tree/PKGBUILD?h=libsearpc
#
# The Seafile RPC Library. Needed by Seafile / CCnet
#
# ##############################################################################################
pkgname=libsearpc
pkgver=3.2.0
gitver=v${pkgver}
pkgrel=1
pkgdesc="The Seafile IPC Server Library"
arch=('i686' 'x86_64')
url="https://github.com/haiwen/libsearpc"
license=('Apache')
depends=('jansson' 'python' 'glib2' 'python-gobject' 'python-simplejson')
provides=(${pkgname})
conflicts=(${pkgname})

build () {
    [[ -d "${srcdir}/${pkgname}-${pkgver}" ]] && rm -rf "${srcdir}/${pkgname}-${pkgver}"
    git clone https://github.com/haiwen/libsearpc.git "${srcdir}/${pkgname}-${pkgver}"
    cd "${srcdir}/${pkgname}-${pkgver}"
    git checkout ${gitver}
    ./autogen.sh
    ./configure --prefix=/usr
    make
}

package () {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
}
