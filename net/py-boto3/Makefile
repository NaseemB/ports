# $OpenBSD: Makefile,v 1.163 2019/05/05 10:48:04 ajacoutot Exp $

COMMENT=		AWS SDK for Python

MODPY_EGG_VERSION=	1.9.142
DISTNAME=		boto3-${MODPY_EGG_VERSION}
PKGNAME=		py-${DISTNAME}

CATEGORIES=		net devel

HOMEPAGE=		https://github.com/boto/boto3

MAINTAINER=		Antoine Jacoutot <ajacoutot@openbsd.org>

# Apache 2.0
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

FLAVORS=		python3
FLAVOR ?=

RUN_DEPENDS=		devel/py-jmespath${MODPY_FLAVOR} \
			devel/py-six${MODPY_FLAVOR} \
			net/py-botocore${MODPY_FLAVOR} \
			net/py-s3transfer${MODPY_FLAVOR}

.if !${FLAVOR:Mpython3}
RUN_DEPENDS +=		devel/py-futures
.endif

TEST_DEPENDS=		${RUN_DEPENDS}

.include <bsd.port.mk>
