# $OpenBSD: Makefile,v 1.27 2018/12/13 19:53:23 sthen Exp $

COMMENT =		the programmer's solid 3D CAD modeller#'
BROKEN-sparc64=	SIGILL on src/cgalutils.cc with CGAL-4.6.3

V =			2015.03-2
DISTNAME =		openscad-${V:S/-/./}
REVISION =		9

CATEGORIES =		cad

HOMEPAGE =		http://www.openscad.org/

# GPLv2+ with CGAL exception
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += CGAL GL GLEW GLU ICE SM X11 Xext Xi Xinerama Xrender
WANTLIB += boost_filesystem-mt boost_program_options-mt boost_regex-mt
WANTLIB += boost_system-mt boost_thread-mt c fontconfig freetype glib-2.0
WANTLIB += gmp harfbuzz iconv intl m mpfr opencsg pthread qscintilla2_qt4
WANTLIB += ${COMPILER_LIBCXX} z lib/qt4/QtGui lib/qt4/QtOpenGL

COMPILER =		base-clang ports-gcc base-gcc

MASTER_SITES =		http://files.openscad.org/
DISTFILES =		openscad-${V}.src.tar.gz

MODULES =		devel/qmake \
			x11/qt4
BUILD_DEPENDS =		devel/bison \
			devel/gettext-tools \
			math/eigen3
LIB_DEPENDS =		devel/boost \
			devel/gmp \
			devel/harfbuzz \
			devel/mpfr \
			editors/qscintilla \
			graphics/glew \
			graphics/opencsg \
			math/cgal

RUN_DEPENDS =		devel/desktop-file-utils \
			fonts/liberation-fonts

# virtual memory exhausted: Cannot allocate memory
.if ${MACHINE_ARCH:Malpha}
COPTS +=		-O1
CXXOPTS +=		-O1
.endif

MODQMAKE_ARGS =		VERSION=${V}
SEPARATE_BUILD =	No

NO_TEST =		Yes

WRKDIST =		${WRKDIR}/openscad-$V

pre-configure:
	ln -sf ${LOCALBASE}/bin/bison ${WRKDIR}/bin/yacc

.include <bsd.port.mk>
