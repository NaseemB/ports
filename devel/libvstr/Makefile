# $OpenBSD: Makefile,v 1.11 2017/06/14 20:01:14 schwarze Exp $

COMMENT =	string library designed for network communication

V =		1.0.15
DISTNAME =	vstr-$V
REVISION =	1

SHARED_LIBS =	vstr-1.0	0.0 \
		vstr		0.0

CATEGORIES =	devel

HOMEPAGE =	http://www.and.org/vstr/

# mostly LGPLv2.1+, assert_loop.c GPLv2+
PERMIT_PACKAGE_CDROM =	Yes
CFLAGS += -fgnu89-inline

MASTER_SITES =		http://www.and.org/vstr/$V/

TEST_FLAGS =		CPPFLAGS="${CPPFLAGS} -I${WRKSRC}/include"

SEPARATE_BUILD =	Yes
USE_GMAKE =		Yes
CONFIGURE_STYLE =	gnu

.include <bsd.port.mk>
.if ${PROPERTIES:Mclang}
CFLAGS += -Wno-expansion-to-defined
.endif
