# $OpenBSD: Makefile,v 1.15 2019/01/06 22:46:28 afresh1 Exp $

COMMENT =	lets you build groups of accessors

MODULES =	cpan
PKG_ARCH =	*
DISTNAME =	Class-Accessor-Grouped-0.10014
CATEGORIES =	devel

MAINTAINER =	Andrew Fresh <afresh1@openbsd.org>

# Perl
PERMIT_PACKAGE_CDROM =	Yes

CONFIGURE_ARGS =	--skipdeps

RUN_DEPENDS =	devel/p5-Module-Runtime>=0.012 \
		devel/p5-Class-XSAccessor>=1.19

TEST_DEPENDS =	devel/p5-Test-Exception>=0.31

# Optional depends to avoid skipping tests
TEST_DEPENDS +=	devel/p5-Devel-Hide \
		devel/p5-Sub-Name>=0.05 \
		devel/p5-Package-Stash

.include <bsd.port.mk>
