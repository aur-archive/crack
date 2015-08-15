# Contributor: Lex Black <autumn-wind at web dot de>
# Contributor: Arno Rehn <arno@arnorehn.de>

pkgname=crack
pkgver=0.10
pkgrel=1
pkgdesc="LLVM based scripting language"
arch=(i686 x86_64)
url="http://code.google.com/p/crack-language/"
license=('MPL')
depends=('llvm-crack')
makedepends=('mesa' 'pcre' 'gtk2' 'sdl' 'libxs')
optdepends=('mesa: OpenGL bindings' 'pcre: bindings' 'gkt2: bindings' 'sdl: bindings' 'libxs: bindings')
source=(http://crack-lang.org/downloads/$pkgname-$pkgver.tar.gz)
sha1sums=('41ae317f7b3047c4c51e94e3b5d42b469942057d')

export LDFLAGS="${LDFLAGS//-Wl,--as-needed}"

prepare() {
  cd "$srcdir/$pkgname-$pkgver"

  sed -i "s;ln -sf \$(DESTDIR)\$(bindir)/;ln -sf ;" Makefile.am
  sed -i "s;ln -sf \$(DESTDIR)\$(bindir)/;ln -sf ;" Makefile.in
}

build() {
  cd "$srcdir/$pkgname-$pkgver"

  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"

  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
