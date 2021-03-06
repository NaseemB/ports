# $OpenBSD: Makefile,v 1.72 2019/03/08 07:05:47 landry Exp $

ONLY_FOR_ARCHS=	aarch64 alpha amd64 arm i386 mips64 mips64el powerpc sparc64 hppa

COMMENT =		Netscape Portable Runtime

VER=			4.21
DISTNAME=		nspr-${VER}

SO_VERSION=		24.0
.for _lib in nspr4 plc4 plds4
SHARED_LIBS+=		${_lib} ${SO_VERSION}
.endfor

CATEGORIES=		devel

HOMEPAGE=		https://developer.mozilla.org/en-US/docs/Mozilla/Projects/NSPR

MAINTAINER=		Landry Breuil <landry@openbsd.org>

WANTLIB=		c pthread

# MPL - Mozilla Public License
PERMIT_PACKAGE_CDROM=	Yes

MASTER_SITES =		http://ftp.mozilla.org/pub/mozilla.org/nspr/releases/v${VER}/src/

USE_GMAKE=		Yes
AUTOCONF_VERSION=	2.69
CONFIGURE_STYLE=	autoconf no-autoheader

MAKE_ENV=		SO_VERSION="${SO_VERSION}"
CONFIGURE_ENV=		${MAKE_ENV}

WRKSRC=			${WRKDIST}/nspr
MODGNU_CONFIG_GUESS_DIRS=${WRKSRC}/build/autoconf

do-test:
	${MAKE_PROGRAM} -C ${WRKSRC}/pr/tests
	${MAKE_PROGRAM} -C ${WRKSRC}/lib/tests
	@cd ${WRKSRC}/pr/tests && ulimit -Sn 192 && env TZ=gmt \
		LD_LIBRARY_PATH=${WRKSRC}/dist/lib /bin/ksh runtests.sh
	LD_LIBRARY_PATH=${WRKSRC}/dist/lib ${WRKSRC}/lib/tests/string
	LD_LIBRARY_PATH=${WRKSRC}/dist/lib ${WRKSRC}/lib/tests/base64t

.include <bsd.port.mk>
