# $OpenBSD: Makefile,v 1.13 2019/04/27 23:55:04 sthen Exp $

COMMENT =		graphical frontend to the objdump disassembler

MODPY_EGG_VERSION = 	9
DISTNAME =		dissy-${MODPY_EGG_VERSION}
CATEGORIES =		devel
HOMEPAGE =		https://github.com/SimonKagstrom/dissy
REVISION =		3

MAINTAINER =		Jonathan Armani <armani@openbsd.org>

# GPLv2
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =	https://distfiles.nl/

MODULES =	lang/python
RUN_DEPENDS =	x11/py-gtk2

NO_TEST =	Yes

.include <bsd.port.mk>
