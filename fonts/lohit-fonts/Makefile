# $OpenBSD: Makefile,v 1.5 2018/06/03 10:54:55 ajacoutot Exp $

PKG_ARCH=	*

COMMENT=	TrueType fonts for Indic scripts

VERSION=	2.5.3
PKGNAME=	lohit-fonts-${VERSION}
CATEGORIES=	fonts x11
HOMEPAGE=	https://pagure.io/lohit
REVISION=	1

MAINTAINER=	Christian Weisgerber <naddy@openbsd.org>

# SIL OFL 1.1
PERMIT_PACKAGE_CDROM=	Yes

MASTER_SITES=	https://releases.pagure.org/lohit/
DIST_SUBDIR=	lohit
.for s in	assamese bengali devanagari gujarati kannada malayalam \
		marathi nepali oriya punjabi tamil tamil-classical telugu
DISTFILES+=	lohit-$s-ttf-${VERSION}.tar.gz
.endfor

NO_BUILD=	Yes
NO_TEST=	Yes

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/fonts/lohit
	${INSTALL_DATA} ${WRKDIST}/*/*.ttf ${PREFIX}/share/fonts/lohit
	${INSTALL_DATA} ${WRKDIST}/lohit-devanagari-ttf-${VERSION}/OFL.txt \
	    ${PREFIX}/share/fonts/lohit

.include <bsd.port.mk>
