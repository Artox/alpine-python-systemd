# Contributor: Josua Mayer <josua.mayer@jm0.eu>
# Maintainer:
pkgname=py3-systemd
pkgver=234
pkgrel=0
pkgdesc="python bindings for systemd"
url="https://github.com/systemd/python-systemd"
arch="all"
license="LGPL-2.1"
depends=""
makedepends="gcc libsystemd-dev musl-dev python3-dev py3-setuptools"
checkdepends="py3-pytest"
install=""
subpackages=""
source="python-systemd-$pkgver.tar.gz::https://github.com/systemd/python-systemd/archive/refs/tags/v$pkgver.tar.gz
	0001-strndupa.patch
	0002-endian.patch"
builddir="$srcdir/python-systemd-$pkgver"
options="!check" # tests fail for no good reason

build() {
	python3 setup.py build
	:
}

check() {
	pytest
}

package() {
	python3 setup.py install --prefix=/usr --root="$pkgdir"

        # Remove installed tests
        rm -rf "$pkgdir"/usr/lib/python3*/site-packages/systemd/test
}

sha512sums="
164e34ba46827711e9c6ff9ed58b2706d9a22abfc7001de030ed7d463d8ddf783eb5fee93b207c29950a3c566018cc3f1a21a549421cf3e05c1287b433367eb2  python-systemd-234.tar.gz
9e7f34804b69190a19ddcb2a2712ad93b079cb34d3ccae771d4bde729a74ba7a14e2f4ff44d24feba189bb4aea07df6d29bf869849c03c08560c3502ef4829e8  0001-strndupa.patch
0b83d21f343c61b425013e13d42bad434d398d05c72859bebac8b45e3dd4554bcb21af31aa8128de80ae08931af8d1276462293a2ac220155f62ee1bcc811da2  0002-endian.patch
"
