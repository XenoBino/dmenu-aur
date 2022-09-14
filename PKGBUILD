pkgname="xenobino-dmenu-git"
pkgver="5.1"
pkgrel="1"
pkgdesc="Suckless's dmenu, patched to my liking"
arch=("x86_64")
depends=("glibc" "libx11" "libxft" "libxinerama" "fontconfig")
provides=("dmenu")
conflicts=("dmenu")
url="https://github.com/XenoBino/dmenu"
license=("MIT")

prepare() {
	if [ -d xenobino-dmenu-git ]; then rm -rf xenobino-dmenu-git; fi
	git clone --depth 1 https://github.com/XenoBino/dmenu xenobino-dmenu-git
}

build() {
	pushd xenobino-dmenu-git &> /dev/null
	make
	popd &> /dev/null
}

package() {
	# DESTDIR: Install to ${pkgdir} for packaging
	# PREFIX: Use /usr instead of /usr/local
	pushd xenobino-dmenu-git &> /dev/null
	make DESTDIR="$pkgdir" PREFIX="/usr" install
	popd &> /dev/null
}
