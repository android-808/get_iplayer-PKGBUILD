# Maintainer: Mark Foxwell <fastfret79@archlinux.org,uk>

pkgname=get_iplayer
pkgver=2.83
pkgrel=1
pkgdesc="Allows you to download or stream any iPlayer programme from the BBC in H.264 (Quicktime/mp4) format, any radio programmes in MP3 or RealAudio format"
arch=('any')
url="http://www.infradead.org/get_iplayer/html/get_iplayer.html"
license=('GPL3')
depends=('perl-libwww' 'perl-html-parser' 'perl-www-mechanize' 'perl-http-cookies' 'perl-net-http' 'perl-xml-simple')
optdepends=('rtmpdump' 'flvstreamer' 'ffmpeg' 'id3v2' 'perl-mp3-info')
conflicts=('get_iplayer', 'get_iplayer-git')
provides=('get_iplayer')
install=$pkgname.install
source=(ftp://ftp.infradead.org/pub/get_iplayer/$pkgname-$pkgver.tar.gz
        'get_iplayer_web_pvr_default'
        'get_iplayer_web_pvr_sh'
        'iplayer-32x32.png' 
        'iplayer-48x48.png'
        'get_iplayer_web_pvr.desktop'
        'launchwindow')
md5sums=('a82613fd389feb87626f1a32df3e3d74'
         'b9584e27941cbccadf3b3ac506479fb4'
         '8baf2ce97929f027a80802f5d8837fdc'
         'ca50a038c6e7da0e90406530511a5254'
         'acd2b5ab30dba8e0ef1730eec6b4012d'
         'c6edc1f643f9217cbfc0b4895807cb1a'
         '38ae66d097e51648be45979a54c8ab8a')

package() {
	cd "$srcdir/$pkgname-$pkgver"
	install -m755 -D get_iplayer $pkgdir/usr/bin/get_iplayer
	install -m644 -D README.md $pkgdir/usr/share/doc/get_iplayer/README.md
	install -m644 -D README-get_iplayer.cgi.txt $pkgdir/usr/share/doc/get_iplayer/README-get_iplayer.cgi.txt
	install -D -m644 get_iplayer.1 ${pkgdir}/usr/share/man/man1/get_iplayer.1
	install -m755 -d $pkgdir/usr/share/get_iplayer/plugins
	install -m644 plugins/*.plugin $pkgdir/usr/share/get_iplayer/plugins/
	install -m755 plugins/plugin.template $pkgdir/usr/share/get_iplayer/plugins/
  install -m755 -D get_iplayer.cgi $pkgdir/usr/share/get_iplayer/
  # Debian changes
  install -D -m644 ../get_iplayer_web_pvr_default $pkgdir/etc/default/get_iplayer_web_pvr
  install -m755 -D ../get_iplayer_web_pvr_sh $pkgdir/usr/bin/get_iplayer_web_pvr
  # Web PVR .desktop changes
  install -m644 -D ../get_iplayer_web_pvr.desktop $pkgdir/usr/share/applications/get_iplayer_web_pvr.desktop
  install -m644 -D ../iplayer-48x48.png $pkgdir/usr/share/icons/hicolor/48x48/apps/iplayer.png
}

# vim:set ts=2 sw=2 et:
