# $OpenBSD: Makefile,v 1.7 2019/03/19 20:12:10 cwen Exp $

COMMENT =		Qt GUI Interface for FluidSynth

DISTNAME =		qsynth-0.5.5

CATEGORIES =		audio

HOMEPAGE =		https://qsynth.sourceforge.io

MAINTAINER=		Sebastian Reitenbach <sebastia@openbsd.org>

# GPLv2+
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =		${MASTER_SITE_SOURCEFORGE:=qsynth/}

WANTLIB += ${COMPILER_LIBCXX} Qt5Core Qt5Gui Qt5Widgets c
WANTLIB += m fluidsynth GL Qt5Network curses readline

.if ${MACHINE_ARCH} == "powerpc"
WANTLIB += atomic
.endif

MODULES =		x11/qt5

LIB_DEPENDS +=		audio/fluidsynth

RUN_DEPENDS +=		devel/desktop-file-utils \
			x11/gtk+3,-guic

USE_GMAKE =		Yes
NO_TEST =		Yes

CONFIGURE_STYLE = 	gnu

CONFIGURE_ENV +=	CPPFLAGS="${CPPFLAGS} -I${LOCALBASE}/include" \
			LDFLAGS="${LDFLAGS} -L${LOCALBASE}/lib -L${X11BASE}/lib"

.include <bsd.port.mk>
