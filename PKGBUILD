# This PKGBUILD only works when inside the repo and not standalone!!!

pkgname=mpd-rich-presence-discord-git
_pkgname=mpd-rich-presence-discord
pkgver=r29
pkgrel=7
pkgdesc="Broadcast your MPD state using discord rich presence!"
arch=('x86_64')
url='https://github.com/second2050'
license=('MIT')
depends=('libmpdclient' 'gcc-libs' 'discord-rpc-api-git')
makedepends=('git' 'cmake' 'discord-rpc-api-git')
#source=("git+https://github.com/second2050/$_pkgname.git")

#md5sums=('SKIP')

build() {
	#cd $srcdir/$_pkgname
	cd $srcdir/..
	./build.sh
}

package() {
	#cd $srcdir/$_pkgname/release
	cd $srcdir/../release
	mkdir -p $pkgdir/usr/bin
	mkdir -p $pkgdir/usr/lib/systemd/system/
	mkdir -p $pkgdir/usr/lib/systemd/user/
	install -Dm755 mpd_discord_richpresence $pkgdir/usr/bin/
	ln -s /usr/bin/mpd_discord_richpresence $pkgdir/usr/bin/mpd-rpc
	install -Dm644 mpd-discord.service $pkgdir/usr/lib/systemd/system/
	install -Dm644 mpd-discord.service $pkgdir/usr/lib/systemd/user/
}

