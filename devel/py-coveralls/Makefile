# $OpenBSD: Makefile,v 1.13 2019/05/08 13:49:47 danj Exp $

COMMENT =	display coverage stats online via coveralls.io

MODPY_EGG_VERSION =	1.6.0
DISTNAME =	coveralls-${MODPY_EGG_VERSION}
PKGNAME =	py-${DISTNAME}
REVISION =	3

CATEGORIES =	devel

HOMEPAGE =	https://github.com/coagulant/coveralls-python

# MIT
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/python

FLAVORS =		python3
FLAVOR ?=

MODPY_PI =		Yes
MODPY_SETUPTOOLS =	Yes

RUN_DEPENDS =		devel/py-docopt${MODPY_FLAVOR} \
			devel/py-coverage${MODPY_FLAVOR} \
			www/py-requests${MODPY_FLAVOR}

NO_TEST =		Yes

post-install:
	mv ${PREFIX}/bin/coveralls ${PREFIX}/bin/coveralls${MODPY_BIN_SUFFIX}

.include <bsd.port.mk>
