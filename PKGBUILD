# $Id: PKGBUILD 67415 2012-03-11 13:48:47Z cbrannon $
# Maintainer:
# Contributor: Aaron Griffin <aaron@archlinux.org>

pkgname=perl-text-wrapi18n
_realname=Text-WrapI18N
pkgver=0.06
pkgrel=5
pkgdesc="Line wrapping module with support for multibyte, fullwidth, and combining characters and languages without whitespaces between words"
arch=('any')
license=('GPL' 'PerlArtistic')
url="http://search.cpan.org/dist/${_realname}/"
depends=('perl-text-charwidth')
options=('!emptydirs')
source=("http://search.cpan.org/CPAN/authors/id/K/KU/KUBOTA/${_realname}-${pkgver}.tar.gz")
md5sums=('0799c16a00926e6c18d400c2e2861d5f')

build() {
  cd ${srcdir}/${_realname}-${pkgver}
  # install module in vendor directories.
  perl Makefile.PL INSTALLDIRS=vendor
  make
  make test
}

package() {
  cd  ${srcdir}/${_realname}-${pkgver}
  make DESTDIR=${pkgdir} install

  # remove perllocal.pod, .packlist, and empty dirs:
  find ${pkgdir} -name '.packlist' -delete
  find ${pkgdir} -name 'perllocal.pod' -delete
}
