# $OpenBSD: Makefile,v 1.14 2017/05/14 17:45:52 danj Exp $

COMMENT = 		Python charting module

MODPY_EGG_VERSION =	0.7.0
DISTNAME = 		pycha-${MODPY_EGG_VERSION}
CATEGORIES = 		graphics

HOMEPAGE = 		http://www.lorenzogil.com/projects/pycha/

# LGPL
PERMIT_PACKAGE_CDROM = 	Yes

MODPY_PI = 		Yes

MODULES = 		lang/python
MODPY_SETUPTOOLS = 	Yes

RUN_DEPENDS = 		graphics/py-cairo
TEST_DEPENDS =		${RUN_DEPENDS}

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/pycha
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/pycha/color
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/pycha
	${INSTALL_DATA} ${WRKSRC}/examples/*.* ${PREFIX}/share/examples/pycha/
	${INSTALL_DATA} ${WRKSRC}/examples/color/* ${PREFIX}/share/examples/pycha/color/
	${INSTALL_DATA} ${WRKSRC}/README.txt ${PREFIX}/share/doc/pycha/

.include <bsd.port.mk>
