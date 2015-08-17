# Maintainer: Konrad Borowski <glitchmr@myopera.com>
pkgname=reg
pkgver=1.2.5
pkgrel=1
pkgdesc="re 'debug' wrapper"
arch=('any')
url='http://search.cpan.org/dist/App-Reg/'
license=('GPL' 'PerlArtistic')
depends=('perl>=5.06.2')
makedepends=('perl-capture-tiny>=0.20')
provides=()
conflicts=()
replaces=()
backup=()
options=('!emptydirs')
install=
source=("http://search.cpan.org/CPAN/authors/id/G/GL/GLITCHMR/App-Reg-$pkgver.tar.gz")
md5sums=('f7253607d4b161ba8e09aba0b2c6bbaf')

build() {
  cd "$srcdir/App-Reg-$pkgver"
  
  # Setting these env variables overwrites any command-line-options we don't want...
  export PERL_MM_USE_DEFAULT=1 PERL_AUTOINSTALL=--skipdeps \
    PERL_MM_OPT="INSTALLDIRS=vendor DESTDIR='$pkgdir'" \
    PERL_MB_OPT="--installdirs vendor --destdir '$pkgdir'" \
    MODULEBUILDRC=/dev/null

  { /usr/bin/perl Makefile.PL &&
    make &&
    make test &&
    make install; } || return 1
}
