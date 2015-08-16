# Maintainer: Limao Luo <luolimao+AUR@gmail.com>
# Contributor: Andrea Scarpino <andrea@archlinux.org>
# Contributor: MeMi69 <MetalMilitia@gmx.net>

pkgname=kdeplasma-applets-activitymanager
pkgver=0.5
pkgrel=2
pkgdesc="Lightweight plasmoid to manage your activities effectively"
arch=(i686 x86_64)
url=http://kde-look.org/content/show.php/Activity+Manager+Plasmoid?content=136278
license=('LGPL')
depends=(kdebase-workspace)
makedepends=(cmake automoc4)
conflicts=(activitymanager-plasmoid)
replaces=(activitymanager-plasmoid)
source=(http://kde-look.org/CONTENT/content-files/136278-activitymanager-$pkgver.tar.bz2)
sha256sums=('68c6602ce6694b005fceb4902cb98c3f3395691f5b302535e490df8f989136b5')
sha512sums=('9e36e09ca7b577931ce29fe1850834a21325462cb74299922347791f97820598557f49f73a9ee29c2f57e877fce9a05cb36c29addb678caddc1af53d5bb7eee7')

build() {
    install -d $pkgname-build/
    cd $pkgname-build/
    cmake ../activitymanager-$pkgver \
        -DCMAKE_INSTALL_PREFIX=$(kde4-config --prefix) \
        -DCMAKE_BUILD_TYPE=Release
    make
}

package() {
    make -C $pkgname-build DESTDIR="$pkgdir" install
}
