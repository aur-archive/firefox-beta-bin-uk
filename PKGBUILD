# Maintainer: Kovivchak Evgen <oneonfire@gmail.com>

pkgname=firefox-beta-bin-uk
_pkgreal=firefox-beta-bin
_pkgnome=firefox-beta
pkgver=38.0esr
pkgrel=1
_lang=uk
_srcurl=ftp://ftp.mozilla.org/pub/firefox/candidates
pkgdesc='Standalone web browser from mozilla.org! Latest beta with Ukrainian language'
url='http://www.mozilla.org/projects/firefox'
arch=('i686' 'x86_64')
depends=('dbus-glib' 'desktop-file-utils' 'libxt' 'mime-types' 'nss' 'shared-mime-info')
license=('MPL' 'GPL' 'LGPL')
provides=('firefox-38.0esr')

_source_x86=(${_srcurl}/${pkgver}-candidates/build1/linux-i686/${_lang}/firefox-${pkgver}.tar.bz2
	     ${_pkgnome}.desktop
	     ${_pkgnome}-safe.desktop)
_md5sums_x86=('2314636cb3639f9c0a0fe32ed7bbf2bd'
	      '560e14d6cfb802255c6f2f71705201dc'
	      'fbd49e056293bc8b4acbda98da857a8f')

_source_x86_64=(${_srcurl}/${pkgver}-candidates/build1/linux-x86_64/${_lang}/firefox-${pkgver}.tar.bz2
	        ${_pkgnome}.desktop
	        ${_pkgnome}-safe.desktop)
_md5sums_x86_64=('b3d3d52ca9d77c13b0eaee738abd4ed6'
         '560e14d6cfb802255c6f2f71705201dc'
         'fbd49e056293bc8b4acbda98da857a8f')

source=(${_source_x86[@]})
md5sums=(${_md5sums_x86[@]})

[ "$CARCH" = "x86_64" ] && source=(${_source_x86_64[@]}) && md5sums=(${_md5sums_x86_64[@]})

package() {
	cd $srcdir

	mkdir -p $pkgdir/{usr/{bin,share/{applications,pixmaps}},opt}
	cp -r firefox $pkgdir/opt/${_pkgreal}-$pkgver

	ln -s /opt/${_pkgreal}-$pkgver/firefox $pkgdir/usr/bin/${_pkgreal}
	install -m644 $srcdir/{$_pkgnome.desktop,$_pkgnome-safe.desktop} $pkgdir/usr/share/applications/
	install -m644 $srcdir/firefox/browser/icons/mozicon128.png $pkgdir/usr/share/pixmaps/${_pkgreal}-icon.png
}
