# Maintainer: Michael W. Lloyd <micl_dev@protonmail.com>
pkgname=python-pcbnewTransition-git
_pkgname=pcbnewTransition
pkgver=v0.3.4.r1.gbd14e1d  # Update this according to the latest version
pkgrel=1
pkgdesc="pcbnewTransition is a python program for ... (add a brief description)"
arch=('any')
url="https://github.com/yaqwsx/pcbnewTransition"
license=('MIT')  # Update this according to the package's license
depends=('python')
makedepends=('python-setuptools' 'python-wheel')
provides=('python-pcbnewTransition')
conflicts=('python-pcbnewTransition' 'python-pcbnewTransition-git')
source=("git+https://github.com/yaqwsx/pcbnewTransition.git")
md5sums=('SKIP')

pkgver() {
  cd "${srcdir}/${_pkgname}"
  # Use the git tag as the version number or any other versioning scheme you prefer
  git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
  cd "${srcdir}/${_pkgname}"
  python3 setup.py sdist bdist_wheel
}

package() {
  cd "${srcdir}/${_pkgname}"
  install -Dm644 "LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"  # Update this line if the package has a different license file
  python3 -m pip install --no-deps --ignore-installed --root="${pkgdir}" --no-warn-script-location dist/*.whl
}
