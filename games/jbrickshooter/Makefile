# $OpenBSD: Makefile,v 1.15 2019/03/24 22:24:13 sthen Exp $

COMMENT =	brick shooter reflexion game

GH_ACCOUNT=	X-Stranger
GH_PROJECT=	jbrickshooter
GH_COMMIT=	0445d9171cc46462970ae8eb08f0c7294c5707df
DISTNAME=	${GH_PROJECT}-1.6.0
CATEGORIES=	games
REVISION=	1

# GPLv3
PERMIT_PACKAGE_CDROM=	Yes

MODULES=	java
MODJAVA_VER=	1.8+

BUILD_DEPENDS=	devel/apache-ant
RUN_DEPENDS=	java/javaPathHelper

NO_TEST=	Yes

do-build:
	cd ${WRKSRC} && mkdir -p build && ant build

do-install:
	${SUBST_CMD} -m 555 -c ${FILESDIR}/jbrickshooter \
		${WRKSRC}/jbrickshooter
	${INSTALL_DATA_DIR} ${PREFIX}/share/jbrickshooter
	cp ${WRKSRC}/build/jbrickshooter.jar ${PREFIX}/share/jbrickshooter
	chown -R ${SHAREOWN}:${SHAREGRP} ${PREFIX}/share/jbrickshooter
	${INSTALL_SCRIPT} ${WRKSRC}/jbrickshooter ${PREFIX}/bin/jbrickshooter

.include <bsd.port.mk>
