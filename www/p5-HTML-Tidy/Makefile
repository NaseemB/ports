# $OpenBSD: Makefile,v 1.18 2018/10/04 09:28:33 benoit Exp $

COMMENT =	(X)HTML validation in a Perl object

DISTNAME =	HTML-Tidy-1.60
CATEGORIES =	www
MODULES =	cpan

MAINTAINER =	Benoit Lecocq <benoit@openbsd.org>

# Perl
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB +=		c perl tidyp

BUILD_DEPENDS =		www/p5-Alien-Tidyp
LIB_DEPENDS =		www/tidyp
TEST_DEPENDS =		devel/p5-Test-Exception

CONFIGURE_ENV +=	LOCALBASE=${LOCALBASE}

.include <bsd.port.mk>
