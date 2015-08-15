# Maintainer: drrossum <youremail@domain.com>
pkgname=edac-utils
pkgver=0.16
pkgrel=3
pkgdesc="Userspace helper for Linux kernel EDAC drivers"
arch=(i686 x86_64)
url='http://sourceforge.net/projects/edac-utils/'
license=('GPL')
depends=('perl' 'sysfsutils')
optdepends=('dmidecode')
source=('http://sourceforge.net/projects/edac-utils/files/edac-utils/0.16/edac-utils-0.16.tar.bz2/download')
md5sums=('77dda84f25ddba732da1d94fe357bf87')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  #./configure --bindir=/usr/bin --libdir=/usr/lib --sbindir=/usr/sbin --includedir=/usr/include --mandir=/usr/share/man --infodir=/usr/share/info
  ./configure --prefix=/usr --sbindir=/usr/bin --sysconfdir=/etc --mandir=/usr/share/man --infodir=/usr/share/info
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"

  make DESTDIR="$pkgdir/" install
  mv $pkgdir/etc/init.d $pkgdir/etc/rc.d
}
