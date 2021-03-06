# $OpenBSD: Makefile,v 1.20 2019/04/28 20:51:59 sthen Exp $

COMMENT=		statistical and novel interactive HTML plots for Python

MODPY_EGG_VERSION=	1.1.0
DISTNAME=		bokeh-${MODPY_EGG_VERSION}
PKGNAME=		py-bokeh-${MODPY_EGG_VERSION}
REVISION=		0

CATEGORIES=		www graphics

HOMEPAGE=		http://bokeh.pydata.org/

MAINTAINER=		Antoine Jacoutot <ajacoutot@openbsd.org>

# BSD
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

FLAVORS=		python3
FLAVOR ?=

RUN_DEPENDS=		devel/py-dateutil${MODPY_FLAVOR} \
			devel/py-six${MODPY_FLAVOR} \
			graphics/py-Pillow${MODPY_FLAVOR} \
			math/py-numpy${MODPY_FLAVOR} \
			textproc/py-yaml${MODPY_FLAVOR} \
			www/py-jinja2${MODPY_FLAVOR} \
			www/py-requests${MODPY_FLAVOR} \
			www/py-tornado${MODPY_FLAVOR}

.if !${FLAVOR:Mpython3}
RUN_DEPENDS +=		devel/py-futures
.endif

NO_TEST=		Yes

post-install:
	mv ${PREFIX}/bin/bokeh ${PREFIX}/bin/bokeh${MODPY_BIN_SUFFIX}

.include <bsd.port.mk>
