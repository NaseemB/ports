# $OpenBSD: Makefile,v 1.15 2019/04/28 20:52:00 sthen Exp $

COMMENT =	very small text templating language

MODPY_EGG_VERSION = 0.5.2
DISTNAME =	Tempita-${MODPY_EGG_VERSION}
PKGNAME =	py-${DISTNAME:L}
REVISION =	2

CATEGORIES =	www

HOMEPAGE =	http://pythonpaste.org/tempita/

# MIT
PERMIT_PACKAGE_CDROM =	Yes

MODPY_PI =	Yes

MODULES =	lang/python

FLAVORS =	python3
FLAVOR ?=

MODPY_SETUPTOOLS =	Yes

TEST_DEPENDS = devel/py-nose${MODPY_FLAVOR}

do-test:
	cd ${WRKSRC} && ${LOCALBASE}/bin/nosetests${MODPY_BIN_SUFFIX}

.include <bsd.port.mk>
