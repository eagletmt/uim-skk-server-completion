# $Id: PKGBUILD 124164 2011-05-17 08:27:15Z bisson $
# Maintainer: Gaetan Bisson <bisson@archlinux.org>
# Contributor: damir <damir@archlinux.org>

pkgname=uim
pkgver=1.7.0
pkgrel=1
pkgdesc='Multilingual input method library'
arch=('i686' 'x86_64')
url='http://code.google.com/p/uim/'
license=('custom:BSD')
depends=('gtk2' 'libxft' 'libedit' 'anthy' 'm17n-lib')
makedepends=('intltool' 'gettext' 'gnome-panel')
optdepends=('gnome-panel: gnome applet indicator')
options=('!libtool')
source=("http://uim.googlecode.com/files/${pkgname}-${pkgver}.tar.bz2"
         server-completion.patch)
sha1sums=('b79ed80c2557e804e6d3d2771a213a29cd932a73'
          'ac72bdd6b0ea92e2e898d2dd88663c2d36a9cc3d')

install=install

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	patch -Np0 -i "$srcdir/server-completion.patch"
	./configure \
		--prefix=/usr \
		--libexecdir=/usr/lib/uim \
		--with-anthy-utf8
	make
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make -j1 DESTDIR="${pkgdir}" install
	install -D -m644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/COPYING"
}
