# Maintainer: Muflone http://www.muflone.com/contacts/english/
# Contributor: archtux <antonio dot arias99999 at gmail dot com>

pkgname=gespeaker
pkgver=0.8.4
pkgrel=1
pkgdesc="A GTK+ frontend for espeak and mbrola to speech the read text."
url="http://www.muflone.com/gespeaker/"
arch=('any')
license=('GPL2')
depends=('espeak' 'librsvg' 'pygtk' 'python2-dbus' 'python2-xdg' 'alsa-utils')
optdepends=('mbrola: for enhanced mbrola voices support'
            'mbrola-voices: at least one mbrola voice'
            'libpulse: PulseAudio output')
provides=('gespeaker')
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/muflone/${pkgname}/archive/${pkgver}.tar.gz")
md5sums=('63c7a8b9ef3db4340eb197e4860dc244')
sha1sums=('ce8987f81f7ff523cd7b127888ed7d59dbd96473')
sha256sums=('1b4465ae54fbcc91a89213b90c2ae55881640abcab84d5150f62b9527b1e96ec')

prepare() {
  cd "${pkgname}-${pkgver}"
  # Python2 fix
  for _file in setup.py gespeaker src/gespeaker.py
  do
    sed -i 's#env python#env python2#' "${_file}"
  done
}

build() {
  cd "${pkgname}-${pkgver}"
  python2 setup.py build
}

package() {
  cd "${pkgname}-${pkgver}"
  python2 setup.py install --optimize=1 --root "${pkgdir}"
}

