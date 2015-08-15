pkgname=gstreamermm-git
pkgver=1.0.10.r54.g69f07ba
pkgrel=1
pkgdesc="C++ interface for GStreamer"
arch=('i686' 'x86_64')
url="http://gstreamer.freedesktop.org/bindings/cplusplus.html"
license=('LGPL')
depends=('glibmm' 'gst-plugins-base' 'libsigc++2.0' 'libxml++')
makedepends=('git' 'doxygen' 'mm-common')
provides=(${pkgname%-*})
conflicts=(${pkgname%-*})
source=('gstreamermm-git::git+https://git.gnome.org/browse/gstreamermm')
sha256sums=('SKIP')

pkgver() {
  cd ${pkgname}
  git describe --long | sed -r 's/([^-]*-g)/r\1/;s/-/./g'
}

build() {
  cd ${pkgname}
  
  #./configure --prefix=/usr
  sh autogen.sh --prefix=/usr
  make
}

package() {
  cd ${pkgname}

  make DESTDIR=${pkgdir} install
}
