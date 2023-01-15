pkgname=colordiff
pkgver=1.0.21
pkgrel=1
pkgdesc="A Perl script wrapper for 'diff' that produces the same output but with pretty 'syntax' highlighting"
arch=('x86_64')
url="https://www.colordiff.org/"
license=('GPL')
depends=('perl' 'diffutils')
backup=('etc/colordiffrc' 'etc/colordiffrc-lightbg')
source=("https://www.colordiff.org/archive/${pkgname}-${pkgver}.tar.gz")
sha256sums=('9b30f4257ef0f0806dea5a27c9ad8edc3f7999f05ddaff6f0627064dc927e615')

package() {
	cd "${pkgname}-${pkgver}"

	make DESTDIR="${pkgdir}" INSTALL_DIR=/usr/bin MAN_DIR=/usr/share/man/man1 install
	install -m644 colordiffrc-lightbg "${pkgdir}/etc/colordiffrc-lightbg"
}
