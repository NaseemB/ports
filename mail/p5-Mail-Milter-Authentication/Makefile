# $OpenBSD: Makefile,v 1.3 2018/01/11 19:27:03 rpe Exp $

COMMENT =	perl implementation of email authentication standards

V =		1.1.0
DISTNAME =	Mail-Milter-Authentication-v${V}
PKGNAME =	p5-Mail-Milter-Authentication-${V}
CATEGORIES =	mail
REVISION =	0

MAINTAINER =	Giovanni Bechis <giovanni@openbsd.org>

# Perl
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		cpan

SUBST_VARS =		VARBASE
pre-configure:
		${SUBST_CMD} ${WRKSRC}/bin/authentication_milter

CONFIGURE_STYLE =	modinst

RUN_DEPENDS =	devel/p5-List-MoreUtils \
		converters/p5-JSON \
		mail/p5-Email-Address \
		mail/p5-Email-Date-Format \
		mail/p5-Mail-DMARC>=1.20150908 \
		sysutils/p5-Proc-ProcessTable

TEST_DEPENDS =	devel/p5-Test-CheckManifest \
		devel/p5-Test-File-Contents \
		devel/p5-Test-Perl-Critic \
		devel/p5-Test-Pod \
		devel/p5-Test-Pod-Coverage

.include <bsd.port.mk>
