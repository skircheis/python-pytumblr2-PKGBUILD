# Maintainer: Siegfried Kircheis < kircheis [dot] siegfried [at] proton [dot] me >

_pkgname=pytumblr2
pkgname=python-$_pkgname-git
pkgver=0.2.4.r245.0a11d32
pkgrel=2
pkgdesc="Python3 wrapper for Tumblr API, nostalgebraist's fork"
arch=('any')
url="https://github.com/nostalgebraist/pytumblr2"
license=('Apache')
depends=('python')
makedepends=(
    'python-setuptools'
    'python-future'
    'python-requests'
    'python-requests-oauthlib'
)
provides=(python-$_pkgname)
source=("$_pkgname::git+https://github.com/nostalgebraist/pytumblr2")
sha256sums=('SKIP')


pkgver() {
    cd "${srcdir}/$_pkgname"
    printf "%s.r%s.%s" "$(python setup.py --version)" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
    # Clean out old wheels etc.
    git -C "$_pkgname" clean -dfx
}


package() {
    cd "${srcdir}/$_pkgname"
    python setup.py install --root="${pkgdir}/"
}
