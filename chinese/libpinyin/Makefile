# $OpenBSD: Makefile,v 1.1.1.1 2019/04/01 04:28:06 kevlo Exp $

COMMENT =	library to deal with pinyin

V =		2.3.0
DISTNAME =	libpinyin-$V
PKGNAME =	zh-libpinyin-$V

SHARED_LIBS +=	pinyin	0.0	# 13.0
SHARED_LIBS +=	zhuyin	0.0	# 13.0

CATEGORIES =	chinese inputmethods

HOMEPAGE =	https://github.com/libpinyin/libpinyin

MAINTAINER =	Kevin Lo <kevlo@openbsd.org>

# GPLv3+
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB +=	${COMPILER_LIBCXX} c db glib-2.0 iconv intl m pcre

MASTER_SITES =	https://github.com/libpinyin/libpinyin/releases/download/$V/

BUILD_DEPENDS =	print/texinfo
LIB_DEPENDS =	databases/db/v4 \
		devel/glib2

USE_GMAKE =	yes
CONFIGURE_STYLE =	gnu
CONFIGURE_ARGS =	--enable-libzhuyin
CONFIGURE_ENV =	CPPFLAGS="-I${LOCALBASE}/include/db4 -I${LOCALBASE}/include" \
		LDFLAGS="-L${LOCALBASE}/lib/db4 -L${LOCALBASE}/lib" \
		MAKEINFO="${LOCALBASE}/bin/gmakeinfo"

.include <bsd.port.mk>
