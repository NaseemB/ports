# $OpenBSD: Makefile,v 1.6 2019/03/24 22:24:14 sthen Exp $

COMMENT =		web application security tool

VERSION =		2.7.0
REVISION =		0
DISTNAME =		ZAP_${VERSION}_Linux
PKGNAME =		zaproxy-${VERSION}

CATEGORIES =		security

HOMEPAGE =		https://www.owasp.org/index.php/ZAP

MAINTAINER =		sebastien dellac <shaxo@laposte.net>

# Apache v2.0 License
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =		https://github.com/zaproxy/zaproxy/releases/download/${VERSION}/
MASTER_SITES +=		${MASTER_SITE_PACKETSTORM:=web/}

MODULES =               java
MODJAVA_VER =           1.8+

RUN_DEPENDS =		java/javaPathHelper

NO_BUILD =		Yes
NO_TEST =		Yes

WRKDIST =		${WRKDIR}/ZAP_${VERSION}

SUBST_VARS +=		VERSION

do-install:
	cp -r ${WRKDIST} ${PREFIX}/share/zaproxy
	${SUBST_PROGRAM} ${FILESDIR}/zaproxy.sh ${PREFIX}/bin/zaproxy

.include <bsd.port.mk>
