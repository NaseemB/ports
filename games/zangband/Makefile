# $OpenBSD: Makefile,v 1.25 2019/04/02 09:01:55 naddy Exp $

COMMENT=	Zangband (Zelazny Angband) with color, X11 support

VERSION=	2.6.2
DISTNAME=	zangband-${VERSION}
REVISION =	5
CATEGORIES=	games
MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=zangband/}

PERMIT_PACKAGE_CDROM=	not-for-profit redistribution only
PERMIT_PACKAGE_FTP=	Yes

WANTLIB=		c ncurses

HOMEPAGE=		http://www.zangband.org/

BUILD_DEPENDS=		${MODGNU_AUTOCONF_DEPENDS} \
			${MODGNU_AUTOMAKE_DEPENDS}

USE_GMAKE=		Yes
MAKE_ENV=		CC="${CC}" CFLAGS="${CFLAGS}"

AUTOCONF_VERSION=	2.54
AUTOMAKE_VERSION=	1.4
CONFIGURE_STYLE=	gnu
CONFIGURE_ENV=		TRUEPREFIX="${TRUEPREFIX}"

WRKDIST=		${WRKDIR}/zangband

FLAVORS=		no_x11
FLAVOR?=	

.if !${FLAVOR:Mno_x11}
CONFIGURE_ARGS+=	--with-x
WANTLIB+=		ICE SM X11 Xaw Xmu Xt xcb
.else
CONFIGURE_ARGS+=	--without-x
.endif

do-gen:
	@cd ${WRKSRC}; ${AUTOCONF_ENV} autoreconf -i

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/zangband
	(cd ${WRKDIST}/lib && tar -cf - * ) | \
	   (cd ${PREFIX}/share/zangband && tar -xf - )
	@chown -R ${SHAREOWN}:games ${PREFIX}/share/zangband
	@find ${PREFIX} \( -name Makefile\* -o -name delete.me \) \
           -exec rm "{}" \;
	${INSTALL} -s -o ${BINOWN} -g games -m 2555 ${WRKSRC}/src/zangband \
	   ${PREFIX}/bin

.include <bsd.port.mk>
