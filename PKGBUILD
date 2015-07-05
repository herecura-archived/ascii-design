# Contributer: giacomogiorgianni@gmail.com 

pkgname=ascii-design
pkgver=1.0.2
pkgrel=1
pkgdesc="Ascii Design is an ascii-art program based on figlet engine."
arch=("i686" "x86_64")
url="http://ascii-design.sourceforge.net/"
license=('GPL')
depends=('qt4' 'figlet' 'figlet-fonts')
makedepends=('cmake')
#source=("http://downloads.sourceforge.net/project/$pkgname/$pkgname/Ascii-Design_1.0/${pkgname}-${pkgver}.tar.bz2")
source=("http://sourceforge.net/projects/${pkgname}/files/${pkgname}/Ascii-Design%20$pkgver/${pkgname}-$pkgver.tar.bz2")
md5sums=('67fc4bda1f3acbd3c8962ef6fb860db4')


build() {
	cd "${pkgname}-${pkgver}"
	if [ -d build ]; then
		msg 'Cleaning previous build...'
		rm -rf build
	fi

	#run cmake manually to set the correct CMAKE_INSTALL_PREFIX
	mkdir build
	cd build
	cmake -DQT_QMAKE_EXECUTABLE=qmake4 -DCMAKE_INSTALL_PREFIX=/usr ..
	make
}

package() {
	cd "${pkgname}-${pkgver}/build"
	make DESTDIR=${pkgdir} install
}
