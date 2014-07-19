# Maintainer: Chris Andrews <christophersimonandrews at gmail dot com>
# Contributor: Phillip Smith <fukawi2@NO-SPAM.gmail.com>

### I AM ONLY THE PACKAGER, NOT THE DEVELOPER
### Please ask support questions about this software in one of:
###   1) The AUR comments; OR
###   2) Upstream forums/maillist etc; OR
###   3) The ArchLinux forums
### I do not always know enough about the software itself, or don't have the
### time to promptly respond to direct emails.
### If you have found a problem with the package/PKGBUILD (as opposed to
### the software) then please do email me or post an AUR comment.

pkgname=gitweb
pkgver=1.9.0
pkgrel=1
pkgdesc="web gui for the fast distributed version control system"
arch=('i686' 'x86_64')
url="http://git-scm.com/"
license=('GPL2')
depends=('curl' 'expat>=2.0' 'perl-error' 'perl>=5.10.0')
source=("http://git-core.googlecode.com/files/git-${pkgver}.tar.gz")
sha1sums=('e60667fc16e5a5f1cde46616b0458cc802707743')
build() {
  cd $srcdir/git-$pkgver

  make configure

  ./configure --prefix=/usr

  make gitweb
}

package() {
  cd $srcdir/git-$pkgver

  make DESTDIR=$pkgdir gitwebdir=/srv/http/gitweb/ install-gitweb
}
