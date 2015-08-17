# $Id$
# Maintainer: David C. Rankin <drankinatty@gmail.com>
#
# All modifications and uses of this file are licensed under
# the software for which this file was made for, should the software
# be under an Open Source License, at least version 1.9, defined
# by the Open Source Initiative. In other cases, this file is automatically
# released to the Public Domain.
#

pkgname=trinity-pyqt3
pkgver=3.18.1
pkgrel=1
pkgdesc="A set of Python bindings for the Qt3 toolkit"
arch=('i686' 'x86_64')
url="http://www.riverbankcomputing.com/software/pyqt/intro"
groups=('trinity-base')
depends=('python2-sip' 'qscintilla-qt3' 'trinity-qt3')
license=('GPL')
provides=('trinity-pyqt3' 'pyqt3')
conflicts=('pyqt3')
replaces=('trinity-pyqt3')
source=("http://www.riverbankcomputing.com/static/Downloads/PyQt3/PyQt-x11-gpl-${pkgver}.tar.gz")
md5sums=('f1d120495d1aaf393819e988c0a7bb7e')

build() {
  cd ${srcdir}/PyQt-x11-gpl-${pkgver}

  . /etc/profile.d/qt3.sh

  export QMAKESPEC="/opt/qt/mkspecs/default"

  echo yes | python2.7 configure.py -q /opt/qt/

  make
}

package() {
  cd ${srcdir}/PyQt-x11-gpl-${pkgver}
  make DESTDIR=${pkgdir} install
}
