# $OpenBSD: Makefile,v 1.16 2017/11/21 00:13:04 naddy Exp $


COMMENT=		RDF Parser Toolkit for Redland
DISTNAME=		raptor2-2.0.15
PKGNAME=		${DISTNAME:C/raptor2/raptor/}
CATEGORIES=		textproc
REVISION=		2

SHARED_LIBS +=  raptor2              0.0      # 0.0

HOMEPAGE=		http://librdf.org/

MASTER_SITES=		http://download.librdf.org/source/

# LGPL 2.1+, GPL 2+ or Apache 2+
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB =  c crypto curl iconv intl lzma m nghttp2 pthread ssl xml2 xslt
WANTLIB += yajl z

LIB_DEPENDS=		devel/libyajl \
			net/curl \
			textproc/libxslt

CONFIGURE_STYLE=	gnu
CONFIGURE_ARGS=		--enable-parsers=all \
			--with-www=curl

.include <bsd.port.mk>
