# $OpenBSD: Makefile,v 1.31 2019/05/08 14:45:23 ian Exp $

COMMENT=compile Java source into .class files (quickly!)

# Jikes, a fast Java compiler.

DISTNAME=	jikes-1.22
REVISION =	9
CATEGORIES=	lang
HOMEPAGE=	http://jikes.sourceforge.net/
MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=jikes/}
EXTRACT_SUFX=	.tar.bz2

MAINTAINER=	Yozo TODA <yozo@v007.vaio.ne.jp>

# IBM Public License
PERMIT_PACKAGE_CDROM=	commercial contributor must indemnify all others
PERMIT_PACKAGE_FTP=	Yes

WANTLIB=		c iconv m ${COMPILER_LIBCXX}

COMPILER =		base-clang ports-gcc base-gcc

LIB_DEPENDS=	converters/libiconv

SEPARATE_BUILD=	Yes
CONFIGURE_STYLE=gnu

CONFIGURE_ENV=	CPPFLAGS="${CPPFLAGS} -I${LOCALBASE}/include" \
		LDFLAGS="${LDFLAGS} -L${LOCALBASE}/lib"

FAKE_FLAGS+=	docdir=${PREFIX}/share/doc/jikes/

.include <bsd.port.mk>
