# $OpenBSD: Makefile,v 1.11 2019/01/05 15:42:44 juanfra Exp $

COMMENT =		decompressor written in C for lzip files

DISTNAME =		lunzip-1.11

HOMEPAGE =		http://lzip.nongnu.org/lunzip.html
MASTER_SITES =		${MASTER_SITE_SAVANNAH:=lzip/lunzip/}

# GPLv2+
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		c

# All other lzip ports use .tar.lz by default.
EXTRACT_SUFX =		.tar.gz

.include <bsd.port.mk>
