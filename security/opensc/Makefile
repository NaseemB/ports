# $OpenBSD: Makefile,v 1.50 2019/04/24 16:26:57 sthen Exp $

COMMENT=	set of libraries and utilities to access smart cards

V=		0.19.0
REVISION=	2
DISTNAME=	opensc-${V}
SUBST_VARS +=	V

SHARED_LIBS +=	opensc 7.0	# 5.0
SHARED_LIBS +=	smm-local 3.0	# 5.0

CATEGORIES=	security

HOMEPAGE=	https://github.com/OpenSC/OpenSC/wiki

# LGPLv2.1+
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB=	c crypto curses ffi gio-2.0 glib-2.0 gmodule-2.0 gobject-2.0 \
		iconv intl pcre pthread readline z

MASTER_SITES=	https://github.com/OpenSC/OpenSC/releases/download/${V}/

BUILD_DEPENDS=	devel/libtool \
		${MODGNU_AUTOCONF_DEPENDS} \
		${MODGNU_AUTOMAKE_DEPENDS} \
		security/pcsc-lite \
		textproc/docbook-xsl
RUN_DEPENDS=	devel/desktop-file-utils \
		security/ccid
LIB_DEPENDS=	devel/glib2

USE_GMAKE=	Yes

CONFIGURE_STYLE=gnu
CONFIGURE_ARGS=	--enable-static \
		--sysconfdir=${SYSCONFDIR} \
		--enable-sm \
		--disable-cryptotokenkit \
		--with-pkcs11-provider=${LOCALBASE}/lib/pkcs11/opensc-pkcs11.so \
		--with-xsl-stylesheetsdir=${LOCALBASE}/share/xsl/docbook
CONFIGURE_ENV=	CPPFLAGS="-I${LOCALBASE}/include/PCSC"

FAKE_FLAGS=	mandir="${PREFIX}/man/" \
		sysconfdir="${PREFIX}/share/examples/opensc/"

AUTOCONF_VERSION = 2.69
AUTOMAKE_VERSION = 1.15

pre-configure:
	cd ${WRKSRC} && env AUTOCONF_VERSION=${AUTOCONF_VERSION} \
		AUTOMAKE_VERSION=${AUTOMAKE_VERSION} autoreconf -f -i

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/lib/pkgconfig
	${SUBST_CMD} -c -m ${NONBINMODE} -o ${BINOWN} -g ${BINGRP} \
	    ${FILESDIR}/libopensc.pc ${PREFIX}/lib/pkgconfig/libopensc.pc
	@find ${PREFIX}/lib/pkcs11/ -name '*.la' -delete

.include <bsd.port.mk>
