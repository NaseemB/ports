# $OpenBSD: Makefile,v 1.11 2018/10/27 07:47:57 bentley Exp $

PKG_ARCH =		*

COMMENT =		font to view stroke order diagrams for Kanji, Kana and etc

DISTNAME =		KanjiStrokeOrders_v4.002
PKGNAME =		ja-${DISTNAME:L:S/_v/-ttf-/}
CATEGORIES =		fonts japanese x11

HOMEPAGE =		http://www.nihilist.org.uk/

# BSD
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =		http://www.nihilist.org.uk/

EXTRACT_SUFX =		.zip

NO_BUILD =		Yes
NO_TEST =		Yes

WRKDIST =		${WRKDIR}

INST_DIR =		${PREFIX}/share/fonts/KanjiStrokeOrders

do-install:
	${INSTALL_DATA_DIR} ${INST_DIR}
	${INSTALL_DATA} ${WRKSRC}/{*.ttf,*.txt} ${INST_DIR}

.include <bsd.port.mk>
