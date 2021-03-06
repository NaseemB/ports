# $OpenBSD: Makefile,v 1.50 2019/04/28 20:51:52 sthen Exp $

COMMENT =	Python module that implements the SSH2 protocol

MODPY_EGG_VERSION =	2.4.1
DISTNAME =		paramiko-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}
CATEGORIES =		security
REVISION =		0

HOMEPAGE =		https://github.com/paramiko/paramiko/

MAINTAINER =		Benoit Lecocq <benoit@openbsd.org>

# LGPL
PERMIT_PACKAGE_CDROM =	Yes

MODPY_PI =		Yes

MODULES =		lang/python

MODPY_SETUPTOOLS =	Yes

RUN_DEPENDS =		devel/py-asn1${MODPY_FLAVOR} \
			security/py-bcrypt${MODPY_FLAVOR} \
			security/py-cryptography${MODPY_FLAVOR} \
			security/py-PyNaCl${MODPY_FLAVOR}
TEST_DEPENDS =		${RUN_DEPENDS} \
			devel/py-nose${MODPY_FLAVOR} \
			devel/py-test${MODPY_FLAVOR}

FLAVORS =		python3
FLAVOR ?=

MODPY_ADJ_FILES =	demos/*.py

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/${MODPY_PY_PREFIX}paramiko
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/${MODPY_PY_PREFIX}paramiko
	cp -R ${WRKSRC}/docs/* ${PREFIX}/share/doc/${MODPY_PY_PREFIX}paramiko
	chown -R ${SHAREOWN}:${SHAREGRP} ${PREFIX}/share/doc/${MODPY_PY_PREFIX}paramiko
	${INSTALL_DATA} ${WRKSRC}/demos/* \
	  ${PREFIX}/share/examples/${MODPY_PY_PREFIX}paramiko

do-test:
	cd ${WRKSRC} && nosetests${MODPY_BIN_SUFFIX}

.include <bsd.port.mk>
