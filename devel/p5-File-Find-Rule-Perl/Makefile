# $OpenBSD: Makefile,v 1.14 2017/12/05 16:25:45 espie Exp $

COMMENT=	common rules for searching for Perl things

MODULES=	cpan
PKG_ARCH=	*
DISTNAME =	File-Find-Rule-Perl-1.15
CATEGORIES=	devel
FIX_EXTRACT_PERMISSIONS=Yes

# Perl
PERMIT_PACKAGE_CDROM=	Yes

RUN_DEPENDS=	devel/p5-File-Find-Rule>=0.20 \
		devel/p5-Params-Util
BUILD_DEPENDS=	${RUN_DEPENDS}

.include <bsd.port.mk>
