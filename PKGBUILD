# Contributor: DeedleFake <deedlefake at users.noreply.github.com>
# Maintainer: barchl <benschau at users.noreply.github.com>

pkgname=complx-git
pkgver=4.15.6.10.g9c9c36b
pkgrel=1
pkgdesc="Complx: LC-3 Simulator used in GT:CS2110, created by Brandon."
arch=('x86_64')
url="https://www.github.com/TricksterGuy/complx"
license=('GPL')
depends=('wxgtk')
makedepends=('git' 'cmake')
provides=('complx')
conflicts=('complx')
source=("${pkgname}::git+${url}")
md5sums=('SKIP')

pkgver() {
    cd "$srcdir/$pkgname"
    git describe --long --tags | sed 's/-/./g'
}

build() {
    mkdir -p "$srcdir/$pkgname/build"
    cd "$srcdir/$pkgname/build"
    cmake ..

    make PREFIX="/usr"
}

package() {
    cd "$srcdir/$pkgname/build"
    sudo make PREFIX="$pkgdir/usr" install

    export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:"/usr/local/lib/"
}
