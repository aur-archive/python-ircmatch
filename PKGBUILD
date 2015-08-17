# Maintainer: Max Teufel <mteufel@urandom.eu.org>

pkgbase=python-ircmatch
pkgname=('python-ircmatch-git' 'python2-ircmatch-git')
pkgver=1.1.11.86d4aeb
pkgrel=1
pkgdesc="python extension for fast IRC mask matching and collapsing"
arch=('any')
url="https://github.com/kaniini/ircmatch"
license=('custom')
makedepends=('python-setuptools' 'python2-setuptools')
options=(!emptydirs)
source=("python-ircmatch-git::git+https://github.com/kaniini/ircmatch.git")
md5sums=('SKIP')

pkgver() {
    cd "${srcdir}/python-ircmatch-git"
    echo "$(python setup.py --version).$(git rev-list --count HEAD).$(git rev-parse --short HEAD)"
}

build() {
    cd "${srcdir}"
    cp -r python-ircmatch-git python2-ircmatch-git
}

package_python-ircmatch-git() {
    depends=('python')
    cd "${srcdir}/python-ircmatch-git"
    python3 setup.py install --root=$pkgdir --optimize=1
    install -Dm644 COPYING $pkgdir/usr/share/licenses/$pkgname/COPYING
}

package_python2-ircmatch-git() {
    depends=('python2')
    cd "${srcdir}/python2-ircmatch-git"
    python2 setup.py install --root=$pkgdir --optimize=1
    install -Dm644 COPYING $pkgdir/usr/share/licenses/$pkgname/COPYING
}
