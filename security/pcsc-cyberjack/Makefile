# $OpenBSD: Makefile,v 1.9 2019/05/04 09:10:10 feinerer Exp $

COMMENT =		REINER SCT cyberJack chipcard reader driver

DISTNAME =		pcsc-cyberjack_3.99.5final.SP13
PKGNAME =		${DISTNAME:S/_/-/}

SHARED_LIBS =		ifd-cyberjack		0.0 # 6.0

CATEGORIES =		security

HOMEPAGE =		https://www.reiner-sct.com/support/

MAINTAINER =		Ingo Feinerer <feinerer@logic.at>

# LGPL2.1+
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ${COMPILER_LIBCXX} m usb-1.0

MASTER_SITES =		https://support.reiner-sct.de/downloads/LINUX/V3.99.5_SP13/

# -std=c++11
COMPILER =		base-clang ports-clang ports-gcc

BUILD_DEPENDS =		${MODGNU_AUTOCONF_DEPENDS} \
			${MODGNU_AUTOMAKE_DEPENDS} \
			devel/libtool \
			security/pcsc-lite
RUN_DEPENDS =		security/pcsc-lite
LIB_DEPENDS =		devel/libusb1

MAKE_FLAGS =		CPPFLAGS=-I${LOCALBASE}/include \
			CXXFLAGS="${CXXFLAGS} -std=c++11 -Wno-c++11-narrowing"

CONFIGURE_STYLE =	gnu
CONFIGURE_ARGS +=	--disable-xml2 \
			--enable-release

AUTOCONF_VERSION =	2.69
AUTOMAKE_VERSION =	1.15

WRKDIST =		${WRKDIR}/${DISTNAME:S/_/-/}

# Remove MSDOS line endings in files needing a patch
post-extract:
	cd ${WRKSRC} && perl -i -pe 's/\r$$//' cjeca32/Debug.cpp \
		cjeca32/RSCTCriticalSection.cpp

do-gen:
	cd ${WRKSRC} && ${AUTOCONF_ENV} autoreconf -fi

.include <bsd.port.mk>
