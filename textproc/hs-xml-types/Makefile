# $OpenBSD: Makefile,v 1.14 2019/04/24 16:26:58 sthen Exp $

COMMENT =		basic types for representing XML

DISTNAME =		xml-types-0.3.6
REVISION =		5
CATEGORIES =		textproc

HOMEPAGE =		https://john-millikin.com/software/haskell-xml/

# MIT
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/ghc

MODGHC_BUILD =		cabal hackage haddock register

MODGHC_PACKAGE_KEY =	KBWVauU3pnf3clHxqFFRXL

RUN_DEPENDS =		devel/hs-text
BUILD_DEPENDS =		${RUN_DEPENDS}

.include <bsd.port.mk>
