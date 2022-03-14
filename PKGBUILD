pkgname=colordiff
pkgver=1.0.20
pkgrel=1
pkgdesc="A Perl script wrapper for 'diff' that produces the same output but with pretty 'syntax' highlighting"
arch=('x86_64')
url="https://www.colordiff.org/"
license=('GPL')
depends=('perl' 'diffutils')
backup=('etc/colordiffrc' 'etc/colordiffrc-lightbg')
source=("https://www.colordiff.org/archive/${pkgname}-${pkgver}.tar.gz")
sha256sums=('e3b2017beeb9f619ebc3b15392f22810c882d1b657aab189623cffef351d7bcd')

package() {
	cd "${pkgname}-${pkgver}"

	make DESTDIR="${pkgdir}" INSTALL_DIR=/usr/bin MAN_DIR=/usr/share/man/man1 install
	install -m644 colordiffrc-lightbg "${pkgdir}/etc/colordiffrc-lightbg"
}
