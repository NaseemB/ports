# $OpenBSD: Makefile,v 1.1.1.1 2019/05/08 07:26:55 bentley Exp $

COMMENT =	EPUB ebook editor

PKGNAME =	sigil-${GH_TAGNAME}

GH_ACCOUNT =	Sigil-Ebook
GH_PROJECT =	Sigil
GH_TAGNAME =	0.9.13

CATEGORIES =	editors

HOMEPAGE =	https://sigil-ebook.com/

# GPLv3+
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ${COMPILER_LIBCXX} ${MODPY_WANTLIB}
WANTLIB += Qt5Concurrent Qt5Core Qt5Gui Qt5Network Qt5PrintSupport
WANTLIB += Qt5Svg Qt5WebKit Qt5WebKitWidgets Qt5Widgets Qt5Xml
WANTLIB += Qt5XmlPatterns c hunspell-1.6 m pcre16 z

COMPILER =		base-clang ports-gcc
MODULES =		devel/cmake \
			lang/python \
			x11/qt5
MODPY_VERSION =		${MODPY_DEFAULT_VERSION_3}
RUN_DEPENDS =		devel/desktop-file-utils \
			textproc/py-lxml${MODPY_FLAVOR}
LIB_DEPENDS =		textproc/hunspell \
			x11/qt5/qtsvg \
			x11/qt5/qtwebkit \
			x11/qt5/qtxmlpatterns

CONFIGURE_ARGS =	-DUSE_SYSTEM_LIBS=ON

NO_TEST =		Yes

.include <bsd.port.mk>
