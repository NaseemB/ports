# $OpenBSD: Makefile,v 1.5 2019/04/28 20:51:56 sthen Exp $

COMMENT=	simple, fast and efficient podcast parser

MODPY_EGG_VERSION=	0.6.4
DISTNAME=	podcastparser-${MODPY_EGG_VERSION}
PKGNAME=	py-${DISTNAME}
CATEGORIES=	textproc
REVISION=	0

MAINTAINER=	Tim Meunier <trondd@kagu-tsuchi.com>

# ISC
PERMIT_PACKAGE_CDROM=	Yes

MODULES=	lang/python

MODPY_PI=	Yes

BUILD_DEPENDS=	textproc/py-sphinx${MODPY_FLAVOR}

TEST_DEPENDS=	devel/py-nose${MODPY_FLAVOR} \
		devel/py-coverage${MODPY_FLAVOR}

FLAVORS=	python3
FLAVOR?=

MAKE_FILE=	makefile
MAKE_ENV=	PYTHON=${MODPY_BIN}

post-build:
	cd ${WRKSRC}/doc && ${MAKE_ENV} ${MAKE_PROGRAM} man \
		SPHINXBUILD=sphinx-build${MODPY_BIN_SUFFIX}

post-install:
	${INSTALL_DATA} ${WRKSRC}/doc/_build/man/podcastparser.1 \
		${PREFIX}/man/man1/podcastparser${MODPY_BIN_SUFFIX}.1

.include <bsd.port.mk>
