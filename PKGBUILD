pkgname=colordiff
pkgver=1.0.18
pkgrel=1
pkgdesc="A Perl script wrapper for 'diff' that produces the same output but with pretty 'syntax' highlighting"
arch=('x86_64')
url="http://www.colordiff.org/"
license=('GPL')
depends=('perl' 'diffutils')
makedepends=('xmlto' 'w3m')
backup=('etc/colordiffrc' 'etc/colordiffrc-lightbg')
source=(http://www.colordiff.org/${pkgname}-${pkgver}.tar.gz)
sha256sums=('29cfecd8854d6e19c96182ee13706b84622d7b256077df19fbd6a5452c30d6e0')

build() {
  cd ${pkgname}-${pkgver}
  msg "### make"
  make
}

package() {
  cd ${pkgname}-${pkgver}
  msg "### make install"
  make DESTDIR="${pkgdir}" INSTALL_DIR=/usr/bin MAN_DIR=/usr/share/man/man1 install
  install -m644 colordiffrc-lightbg "${pkgdir}/etc/colordiffrc-lightbg"

  _docdir=${pkgdir}/usr/share/doc/${pkgname}
  _licdir=${pkgdir}/usr/share/licenses/${pkgname}
  install -dm755 ${_docdir} ${_licdir}
  install -Dpm644 BUGS CHANGES INSTALL README ${_docdir}/
  install -Dpm644 COPYING ${_licdir}/
}
