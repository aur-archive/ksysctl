# Mantainer: Alfredo Enrique Jimenez Zúniga<fq_jizu_jerm4@yahoo.com.mx>
# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=ksysctl
pkgver=0.2
pkgrel=2
pkgdesc="A front end for the systemctl program"
arch=('i686' 'x86_64')
url="http://kde-apps.org/content/show.php/KSysCtl?content=148648"
license=('GPL')
depends=('qt4' 'systemd')
source=("http://kde-apps.org/CONTENT/content-files/148648-${pkgname}-${pkgver}.tgz"
	"${pkgname}.desktop")
md5sums=('03c8d49fc2bee16710a44fb3fea2f177'
	 'd02d2ca4ebade0207714cce729a514f9')

build() {
  cd ksysctl
  qmake-qt4
  make
  lrelease-qt4 ksysctl.pro  
}

package() {
  cd ksysctl
  install -d "${pkgdir}"/usr/share/ksysctl
  install -m644 translations/ksysctl_{de_DE,en_GB,en_US}.qm "${pkgdir}"/usr/share/ksysctl/
  install -Dm644 icons/ksysctl.png "${pkgdir}"/usr/share/pixmaps/ksysctl.png
  install -Dm755 ksysctl "${pkgdir}"/usr/bin/ksysctl
  
  install -Dm644 "${srcdir}"/ksysctl.desktop \
    "${pkgdir}"/usr/share/applications/ksysctl.desktop
}