pkgname=devtools-arch4edu-extra
pkgver=21.27a741d
pkgrel=1
pkgdesc='Extra tools for arch4edu package maintainers'
arch=('x86_64' 'armv7h' 'aarch64')
url="https://github.com/arch4edu/$pkgname"
license=('GPL')
depends=('devtools')
makedepends=('git')
source=("git+${url}.git#branch=master")
sha256sums=('SKIP')

pkgver() {
	cd "$srcdir/$pkgname"
	echo "$(git rev-list --count master).$(git rev-parse --short master)"
}

package() {
	cd "$srcdir/$pkgname"
	install -d $pkgdir/usr/bin
	install -d $pkgdir/usr/share/devtools

	if [ "$CARCH" = 'x86_64' ]
	then
		ln -sf /usr/bin/archbuild $pkgdir/usr/bin/arch4edu-x86_64-build
		cat /usr/share/devtools/pacman-extra.conf arch4edu.conf > $pkgdir/usr/share/devtools/pacman-arch4edu.conf
		cat /usr/share/devtools/pacman-extra.conf arch4edu.conf > $pkgdir/usr/share/devtools/pacman-multilib-arch4edu.conf
	else
		for i in armv7h aarch64
		do
			cp $srcdir/$pkgname/pacman-extra-$i.conf $pkgdir/usr/share/devtools/
			cp $srcdir/$pkgname/makepkg-$i.conf $pkgdir/usr/share/devtools/
			ln -sf /usr/bin/archbuild $pkgdir/usr/bin/extra-$i-build
		done
	fi
}
