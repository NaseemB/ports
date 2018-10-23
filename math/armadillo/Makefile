# $OpenBSD: Makefile,v 1.1.1.1 2018/10/21 16:13:57 espie Exp $

COMMENT = 	C++ library for scientific computing
DISTNAME = 	armadillo-9.100.5
SHARED_LIBS = 	armadillo 0.0	# 9.100
CATEGORIES = 	math
HOMEPAGE = 	http://arma.sourceforge.net/
MAINTAINER =	Marc Espie <espie@openbsd.org>

# MPL v2
PERMIT_PACKAGE_CDROM = Yes

WANTLIB = 	${COMPILER_LIBCXX} arpack blas hdf5 lapack m z gfortran

MASTER_SITES =	${MASTER_SITE_SOURCEFORGE:=arma/}
EXTRACT_SUFX= 	.tar.xz

COMPILER = 	base-clang ports-gcc
MODULES += 	devel/cmake

LIB_DEPENDS += 	math/arpack \
		math/hdf5

CONFIGURE_STYLE = cmake
CONFIGURE_ARGS += -DCMAKE_INSTALL_PREFIX=${PREFIX}

NO_TEST = 	Yes

.include <bsd.port.mk>