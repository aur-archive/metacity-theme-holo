# Maintainer: Elias Autio <wompatti@fffin.com>
pkgname=metacity-theme-holo
pkgver=20120508
pkgrel=1
pkgdesc="A GTK3 theme from tiheum, the Faenza icon set creator, that mimics Ice Cream Sandwich (Android 4) theme."
url="http://tiheum.deviantart.com/art/Holo-280076980"
license=('GPL3')
arch=('any')
depends=('gtk-engine-unico' 'gnome-themes-standard')

_gitroot='git://github.com/r3gis3r/Holo-Gnome3-Theme.git'
_gitname='Holo-Gnome3-Theme'

build() {
  cd "${srcdir}"
  msg "Connecting to GIT server...."

  if [[ -d "${_gitname}" ]]; then
    cd "${_gitname}" && git pull origin
    msg "The local files are updated."
  else
    git clone "${_gitroot}"
  fi

  msg "GIT checkout done or server timeout"
  msg "Starting build..."

  rm -rf "${srcdir}/${_gitname}-build"
  git clone "${srcdir}/${_gitname}" "${srcdir}/${_gitname}-build"
  cd "${srcdir}/${_gitname}-build"
}

package() {
    cd $srcdir/${_gitname}
    mkdir -p $pkgdir/usr/share/themes/Holo/
    cp -r metacity-1 "$pkgdir/usr/share/themes/Holo/";
}
