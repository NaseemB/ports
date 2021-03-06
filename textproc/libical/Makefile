# $OpenBSD: Makefile,v 1.39 2019/04/28 20:51:55 sthen Exp $

COMMENT-main=		implementation of the iCalendar protocols and data units
COMMENT-glib=		GObject wrapper for libical library

V=			3.0.4
SUBST_VARS=		V
DISTNAME=		libical-${V}

PKGNAME-main=		${PKGNAME}
PKGNAME-glib=		libical-glib-${V}
REVISION-glib=		2
REVISION-main=		2

SHARED_LIBS +=  ical                 4.1
SHARED_LIBS +=  icalss               4.0
SHARED_LIBS +=  icalvcal             3.0
SHARED_LIBS +=  ical_cxx             1.0
SHARED_LIBS +=  icalss_cxx           1.0
SHARED_LIBS +=  ical-glib            0.0

CATEGORIES=		textproc

HOMEPAGE=		https://libical.github.io/libical/

MAINTAINER=		Antoine Jacoutot <ajacoutot@openbsd.org>

# dual MPLv2, LGPLv2.1
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += icui18n icuuc
WANTLIB-main += ${WANTLIB} ${COMPILER_LIBCXX} m lib/db4/db
WANTLIB-glib += ${WANTLIB} ical glib-2.0 gobject-2.0 intl pthread

COMPILER =		base-clang ports-gcc base-gcc

MASTER_SITES=		https://github.com/libical/libical/releases/download/v${V}/

MULTI_PACKAGES=		-main -glib

MODULES=		devel/cmake

BUILD_DEPENDS=		devel/gobject-introspection \
			lang/vala \
			textproc/libxml

LIB_DEPENDS-main=	databases/db/v4 \
			textproc/icu4c

LIB_DEPENDS-glib=	devel/glib2 \
			${BASE_PKGPATH},-main=${V}


CONFIGURE_ARGS=		-DGOBJECT_INTROSPECTION=true \
			-DICAL_GLIB_VAPI=true \
			-DICAL_BUILD_DOCS=false

CFLAGS +=		-I${LOCALBASE}/include

# needed for libical-glib tests
MODULES +=		lang/python
MODPY_VERSION=		${MODPY_DEFAULT_VERSION_3}
MODPY_RUNDEP=		No
TEST_DEPENDS=		${MODPY_RUN_DEPENDS} \
			textproc/libical,-glib=${V}

pre-configure:
	${SUBST_CMD} ${WRKSRC}/cmake/modules/FindBDB.cmake

.include <bsd.port.mk>
