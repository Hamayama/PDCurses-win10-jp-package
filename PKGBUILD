# Maintainer: Alexey Pavlov <alexpux@gmail.com>
# Contributor: Simon Sobisch <simonsobisch@gnu.org>
# Modification: Hamayama <fkyo0985@gmail.com>

PKGEXT='.pkg.tar.xz'
_realname=pdcurses-win10-jp
pkgbase=mingw-w64-${_realname}
pkgname="${MINGW_PACKAGE_PREFIX}-${_realname}"
pkgver=3.9
pkgrel=14
pkgdesc="Public Domain Curses wincon port for windows 10 jp (mingw-w64)"
arch=('any')
url="https://github.com/Hamayama/PDCurses-win10-jp"
license=('public domain')
makedepends=("${MINGW_PACKAGE_PREFIX}-gcc")
depends=("${MINGW_PACKAGE_PREFIX}-gcc-libs")
options=('staticlibs' 'strip')
source=(${_realname}-${pkgver}.tar.gz::"https://github.com/Hamayama/PDCurses-win10-jp/archive/master.tar.gz")
sha256sums=('SKIP')
conflicts=(${MINGW_PACKAGE_PREFIX}-pdcurses ${MINGW_PACKAGE_PREFIX}-pdcurses-win8-jp)

build() {
  cd "${srcdir}/PDCurses-win10-jp-master"

  make clean

  make \
    CC=${MINGW_PREFIX}/bin/gcc \
    LINK=${MINGW_PREFIX}/bin/gcc \
    STRIP=${MINGW_PREFIX}/bin/strip \
    AR=${MINGW_PREFIX}/bin/ar
}

package() {
  cd "${srcdir}/PDCurses-win10-jp-master"

  mkdir -p ${pkgdir}${MINGW_PREFIX}/{bin,include,lib}
  mkdir ${pkgdir}${MINGW_PREFIX}/include/pdcurses

  export RESULT_DIR=0000_dist
  install $RESULT_DIR/bin/pdcurses.dll      ${pkgdir}${MINGW_PREFIX}/bin/
  install $RESULT_DIR/lib/libpdcurses.dll.a ${pkgdir}${MINGW_PREFIX}/lib/

  install -m 0644 $RESULT_DIR/include/pdcurses.h          ${pkgdir}${MINGW_PREFIX}/include/
  install -m 0644 $RESULT_DIR/include/pdcurses/curses.h   ${pkgdir}${MINGW_PREFIX}/include/pdcurses/
  install -m 0644 $RESULT_DIR/include/pdcurses/curspriv.h ${pkgdir}${MINGW_PREFIX}/include/pdcurses/
  install -m 0644 $RESULT_DIR/include/pdcurses/panel.h    ${pkgdir}${MINGW_PREFIX}/include/pdcurses/
}
