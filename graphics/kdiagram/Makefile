# $OpenBSD: Makefile,v 1.2 2019/03/08 20:00:45 cwen Exp $

COMMENT =	libraries for creating business diagrams

VERSION =	2.6.1
DISTNAME =	kdiagram-${VERSION}
REVISION =	0

CATEGORIES =	graphics

SHARED_LIBS +=  KChart                    0.0 # 2.6
SHARED_LIBS +=  KGantt                    0.0 # 2.6

MAINTAINER =	Rafael Sadowski <rsadowski@openbsd.org>

# GPLv2+
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ${COMPILER_LIBCXX} Qt5Core Qt5Gui Qt5PrintSupport Qt5Svg
WANTLIB += Qt5Widgets c m

MASTER_SITES =	${MASTER_SITE_KDE:=stable/kdiagram/${VERSION}/}

MODULES =	devel/cmake \
		devel/kf5

LIB_DEPENDS +=	x11/qt5/qtsvg

TEST_IS_INTERACTIVE =	X11

.include <bsd.port.mk>
