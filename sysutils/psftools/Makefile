# $OpenBSD: Makefile,v 1.6 2019/03/30 21:21:42 fcambus Exp $

PORTROACH =	ignore:1

COMMENT =	conversion tools for .PSF fonts

DISTNAME =	psftools-1.0.12
SHARED_LIBS +=	psf	0.0	# 1.1

CATEGORIES =	sysutils

HOMEPAGE =	http://www.seasip.info/Unix/PSF/

MAINTAINER =	Frederic Cambus <fcambus@openbsd.org>

# GPLv2+
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB +=	c

MASTER_SITES =	${HOMEPAGE}

CONFIGURE_STYLE = gnu

USE_GMAKE =	Yes

.include <bsd.port.mk>
