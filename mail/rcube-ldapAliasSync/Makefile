# $OpenBSD: Makefile,v 1.7 2018/12/21 12:59:22 sthen Exp $

COMMENT=	roundcube plugin: LDAP Alias Sync

GH_ACCOUNT=	brenard
GH_PROJECT=	ldapAliasSync
GH_COMMIT=	73f9644eb181f39aa98ca5e173d3b2e74155bf7b

DISTNAME=	rcube-ldapAliasSync-20170701
DISTFILES=	${DISTNAME}{${GH_COMMIT}}${EXTRACT_SUFX}

CATEGORIES=	mail www

HOMEPAGE=	https://github.com/dim-0/ldapAliasSync/

# GPLv3+
PERMIT_PACKAGE_CDROM=	Yes

NO_BUILD=	Yes
NO_TEST=	Yes
PKG_ARCH=	*

PREFIX=		${VARBASE}/www
INSTDIR=	${PREFIX}/roundcubemail/plugins
TINSTDIR=	${TRUEPREFIX}/roundcubemail/plugins
SUBST_VARS=	INSTDIR TINSTDIR

MODULES=	lang/php
RUN_DEPENDS=	mail/roundcubemail>=1.1 \
		lang/php/${MODPHP_VERSION},-ldap

do-install:
	${INSTALL_DATA_DIR} ${INSTDIR}/ldapAliasSync
	cp -Rp ${WRKDIST}/* ${INSTDIR}/ldapAliasSync
	chown -R ${SHAREOWN}:${SHAREGRP} ${INSTDIR}
	find ${INSTDIR} \( -name \*.orig -or -name \*.src \) -exec rm -f {} \;

.include <bsd.port.mk>
