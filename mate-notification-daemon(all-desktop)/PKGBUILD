# Maintainer:   Νικόλαος Κυριάκος Φυτίλης <n-fit@live.com>
# Contributor:  eadrom <eadrom@archlinux.info>
# Contributor:  Martin Wimpress <code@flexion.org>

_ver=1.17
_pkgbase=mate-notification-daemon
pkgname="mate-notification-daemon"
pkgver=${_ver}.0
pkgrel=5
provides=('notification-daemon' "${_pkgbase}" "${_pkgbase}-gtk3")
pkgdesc="Notification daemon for MATE (GTK3 version)"
url="http://mate-desktop.org"
arch=('i686' 'x86_64')
conflicts=("${_pkgbase}" "${_pkgbase}-gtk3")
license=('GPL' 'LGPL')
depends=('dconf' 'dbus-glib' 'glib2' 'gtk3' 'gtk-update-icon-cache'
         'libcanberra' 'libwnck3' 'libwnck3' 'libnotify')
makedepends=('mate-common')
source=("https://github.com/spookykidmm/mate-notification-daemon/archive/master.zip")
sha1sums=('469f613cfae2832902d19f14ad73264fdfa92f88')

build() {
    cd $HOME/mate-notification-daemon-dev/src/mate-notification-daemon-master
    ./configure \
        --prefix=/usr \
        --libexecdir=/usr/lib/${_pkgbase} \
        --with-gtk=3.0 \
        --disable-static
    make
}

package() {
    groups=('mate')
cd $HOME/mate-notification-daemon-dev/src/mate-notification-daemon-master
    make DESTDIR="${pkgdir}" install
}
