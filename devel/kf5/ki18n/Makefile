# $OpenBSD: Makefile,v 1.10 2019/03/30 09:13:51 rsadowski Exp $

COMMENT =	KDE Gettext-based UI text internationalization
DISTNAME =	ki18n-${VERSION}

SHARED_LIBS =	KF5I18n		4.3

WANTLIB += ${COMPILER_LIBCXX} Qt5Core Qt5Network Qt5Qml intl m

MODULES +=	lang/python

BUILD_DEPENDS =	devel/gettext-tools \
		x11/qt5/qtscript

LIB_DEPENDS =	devel/gettext \
		x11/qt5/qtdeclarative

# for tests
PORTHOME =	${WRKDIR}

# Calling compileall.py isn't needed, the ts-pmap-compile script
# gets called with "${PYTHON} -B ...".

.include <bsd.port.mk>
