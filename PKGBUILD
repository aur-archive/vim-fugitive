# Maintainer: M Rawash <mrawash@gmail.com>
# Contributor: János Illés <ijanos@gmail.com>
pkgname=vim-fugitive
pkgver=20111227
pkgrel=1
pkgdesc="A git wrapper so awesome, it should be illegal. Latest git version"
arch=('any')
url="http://www.vim.org/scripts/script.php?script_id=2975"
license=('custom:vim')
groups=('vim-plugins')
depends=('vim' 'git')
makedepends=('git')
install=vimdoc.install
_gitroot='git://github.com/tpope/vim-fugitive.git'
_gitname='vim-fugitive'

build() {
  cd "$srcdir"
  msg "Connecting to GIT server...."

  if [ -d $_gitname ] ; then
    cd $_gitname && git pull origin
    msg "The local files are updated."
  else
    git clone $_gitroot $_gitname
  fi

  msg "GIT checkout done or server timeout"
  cd ${srcdir}/vim-fugitive

  installpath="${pkgdir}/usr/share/vim/vimfiles"

  install -Dm644 doc/fugitive.txt $installpath/doc/fugitive.txt
  install -Dm644 plugin/fugitive.vim $installpath/plugin/fugitive.vim


}

# vim:set ts=2 sw=2 et:
