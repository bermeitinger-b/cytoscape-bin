# Maintainer: Bernhard Bermeitinger <bernhard.bermeitinger@gmail.com>
# Contributor: lukaszimmermann <luk.zim91@gmail.com>
# Contributor: eomarjee <eyaz.omarjee+arch@gmail.com>
# Contributor: florianbw <florian.bw@gmail.com>

pkgname=cytoscape-bin
pkgver=3.7.2
pkgrel=0
pkgdesc='A software for visualizing molecular interaction networks and integration with gene expression profiles and other state data.'
arch=('any')
url=http://www.cytoscape.org
license=('LGPL2')
depends=('java-runtime-headless=8')
provides=('cytoscape')
source=("https://github.com/cytoscape/cytoscape/releases/download/${pkgver}/cytoscape-${pkgver}.tar.gz" \
        "cytoscape.desktop" \
        "cytoscape.png" \
        "cytoscape")

sha256sums=('cce74c2ca353b1d0d7ef9515ee70ef34918b308080fa50b515be2ebc517ebb88'
            'f4476545086f845e1cec5861169270da9f82a6ad4944972010827a567af0c7d0'
            '135faa3f0beb8ecc1b704cf376408e8bd5f62f32ba50a84002c14321d0bb0b68'
            '78dd0b17e872eb30035080f0a27f4d9f6e8ffe9e7c78baae3a1d0237d7a2e205')

build() {
  cd ${srcdir}/cytoscape-unix-${pkgver}
  ./gen_vmoptions.sh
}

package() {
  install -d ${pkgdir}/opt/cytoscape
  install -d ${pkgdir}/opt/cytoscape/framework/instances
  install -d ${pkgdir}/usr/share/{applications,pixmaps}
  install -d ${pkgdir}/usr/bin

  cd ${startdir}/
  cp -r ${srcdir}/cytoscape-unix-${pkgver}/* ${pkgdir}/opt/cytoscape
  chmod 755 ${pkgdir}/opt/cytoscape/cytoscape.sh 
  install -D -m755 cytoscape ${pkgdir}/usr/bin/
  install -D -m644 cytoscape.png ${pkgdir}/usr/share/pixmaps
  install -D -m644 cytoscape.desktop ${pkgdir}/usr/share/applications
}

# vim:set ts=2 sw=2 et:
