# $OpenBSD: Makefile,v 1.8 2018/10/24 14:28:11 sthen Exp $

COMMENT =		simple, small and efficient C++ XML parser

GH_ACCOUNT =		leethomason
GH_PROJECT =		tinyxml2
GH_TAGNAME =		4.0.1
REVISION =		2

SHARED_LIBS +=		tinyxml2	1.0 # 3.0

CATEGORIES =		textproc

HOMEPAGE =		http://www.grinninglizard.com/tinyxml2/index.html

# zlib
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB +=		m ${COMPILER_LIBCXX}

COMPILER =		base-clang ports-gcc base-gcc

MODULES =		devel/cmake

pre-patch:
	perl -i -pe 's/\r$$//' ${WRKSRC}/xmltest.cpp

do-test:
	cd ${WRKSRC} && ${CXX} xmltest.cpp tinyxml2.cpp tinyxml2.h && ./a.out

.include <bsd.port.mk>
