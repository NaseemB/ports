# $OpenBSD: Makefile,v 1.32 2019/04/02 09:53:40 naddy Exp $

COMMENT=	portable OTR messaging library and toolkit

DISTNAME=	libotr-4.1.1
CATEGORIES=	security
REVISION=	1

SHARED_LIBS +=  otr                  4.1      # 6.0

HOMEPAGE=	http://otr.cypherpunks.ca/

MASTER_SITES=	${HOMEPAGE}

MAINTAINER =	Pascal Stumpf <pascal@stumpf.co>

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB =  c gcrypt gpg-error iconv intl

LIB_DEPENDS=	security/libgcrypt

# non-shared does not inherit LIB_DEPENDS
LIB_DEPENDS +=	security/libgpg-error

USE_LIBTOOL = 		gnu

CONFIGURE_STYLE=	gnu
# PIE is taken care of on a per-arch basis on OpenBSD, and stack
# protection is enabled anyway.
CONFIGURE_ARGS=		--disable-gcc-hardening \
			--disable-linker-hardening

.include <bsd.port.mk>
