# $OpenBSD: Makefile,v 1.9 2018/09/04 12:46:12 espie Exp $

COMMENT =		replacement for Comic Sans font

TYPEFACE =		comic-neue
VERSION =		2.3
DISTNAME =		${TYPEFACE}-${VERSION}
REVISION =		0

CATEGORIES =		fonts

HOMEPAGE =		http://comicneue.com/

MAINTAINER =		Tristan Le Guern <tleguern@bouledef.eu>

# CC0 (public domain)
# http://creativecommons.org/publicdomain/zero/1.0/
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =		http://comicneue.com/

MODULES =		font

NO_BUILD =		Yes
NO_TEST =		Yes

FONT_DISTDIR =		${WRKDIR}/Web
FCDIR =			${PREFIX}/share/comic-neue

post-install:
	${INSTALL_DATA_DIR} ${FCDIR}
	${INSTALL_DATA} ${FILESDIR}/30-comic-sans-aliases.conf ${FCDIR}

.include <bsd.port.mk>
