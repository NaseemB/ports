# $OpenBSD: Makefile,v 1.28 2019/05/05 04:31:22 bentley Exp $

COMMENT=	library for communicating with an icecast server

DISTNAME=	libshout-2.3.1
REVISION=	0
SHARED_LIBS=	shout	5.1
CATEGORIES=	net audio

HOMEPAGE=	https://icecast.org/

# LGPL
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += m ogg pthread speex theora>=1 vorbis>=4

MASTER_SITES=	https://downloads.xiph.org/releases/libshout/

LIB_DEPENDS=	audio/libvorbis \
		audio/speex \
		multimedia/libtheora

# LIB_DEPENDS don't propagate if !shared
LIB_DEPENDS +=	audio/libogg

FAKE_FLAGS=	docdir='${PREFIX}/share/examples/libshout'

CONFIGURE_STYLE= gnu

SEPARATE_BUILD=	Yes

.include <bsd.port.mk>
