# $OpenBSD: Makefile,v 1.5 2019/04/25 15:04:44 jca Exp $

COMMENT =	manage and share secrets using GnuPG and Git

DISTNAME =	keyringer-0.5.4

CATEGORIES =	security

HOMEPAGE =	https://keyringer.pw/

MAINTAINER =	Gregoire Jadi <gjadi@omecha.info>

# GPLv3+
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =		https://keyringer.pw/releases/
EXTRACT_SUFX =		.tar.bz2

RUN_DEPENDS =		devel/git \
			security/gnupg2 \
			shells/bash \
			converters/base64

MAKE_FLAGS =		PREFIX="${PREFIX}" \
			MANDIR="${PREFIX}/man"

NO_BUILD =		Yes
NO_TEST =		Yes

PKG_ARCH =		*

.include <bsd.port.mk>
