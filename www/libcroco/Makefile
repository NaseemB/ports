# $OpenBSD: Makefile,v 1.32 2019/04/16 08:07:32 ajacoutot Exp $

COMMENT=		generic CSS parsing library for GNOME project

GNOME_PROJECT=		libcroco
GNOME_VERSION=		0.6.13

SHARED_LIBS +=  croco-0.6            4.0      # 3.1

CATEGORIES=		www textproc devel

HOMEPAGE=		http://www.freespiders.org/projects/libcroco/

MAINTAINER=		Antoine Jacoutot <ajacoutot@openbsd.org>

# LGPLv2.1
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += c glib-2.0 iconv intl lzma m pcre pthread xml2 z

MODULES=		x11/gnome

LIB_DEPENDS=		devel/glib2 \
			textproc/libxml

CONFIGURE_STYLE=	gnu

# error: -Bsymbolic-functions requested but not supported by ld
CONFIGURE_ARGS +=	--disable-Bsymbolic

.include <bsd.port.mk>
