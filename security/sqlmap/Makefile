# $OpenBSD: Makefile,v 1.17 2019/04/27 23:55:04 sthen Exp $

COMMENT =		penetration testing tool to detect/exploit SQL injection

GH_ACCOUNT =		sqlmapproject
GH_PROJECT =		sqlmap
GH_TAGNAME =		1.3.3

CATEGORIES =		security

HOMEPAGE =		http://sqlmap.org/

MAINTAINER =		sebastien dellac <shaxo@laposte.net>

# GPLv2
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/python

MODPY_ADJ_FILES	= 	sqlmap.py

# NO_BUILD but needs ${MODPY_LIBDIR}/compileall.py
BUILD_DEPENDS +=	${_MODPY_BUILD_DEPENDS}

NO_BUILD =		Yes
NO_TEST =		Yes

INSTDIR =		${PREFIX}/share/sqlmap

do-install:
	cp -r ${WRKDIST} ${INSTDIR}
	rm ${INSTDIR}/{.{gitattributes,gitignore},README.md}
	rm -rf ${INSTDIR}/doc
	ln -s ${TRUEPREFIX}/share/sqlmap/sqlmap.py ${PREFIX}/bin/sqlmap
	${MODPY_BIN} ${MODPY_LIBDIR}/compileall.py ${INSTDIR}

.include <bsd.port.mk>
