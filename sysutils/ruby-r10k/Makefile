# $OpenBSD: Makefile,v 1.19 2019/02/26 16:35:32 sebastia Exp $

COMMENT =	Puppet module management

DISTNAME =	r10k-3.1.1
CATEGORIES =	sysutils
HOMEPAGE =	https://github.com/puppetlabs/r10k
MAINTAINER =	Sebastian Reitenbach <sebastia@openbsd.org>

# Apache 2.0
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/ruby
BUILD_DEPENDS +=	${RUN_DEPENDS}
RUN_DEPENDS += converters/ruby-multi_json,${MODRUBY_FLAVOR}>=1.10,<2 \
		devel/ruby-colored,${MODRUBY_FLAVOR}=1.2 \
		devel/ruby-cri,${MODRUBY_FLAVOR}>=2.15.1,<2.16 \
		devel/ruby-gettext-setup,${MODRUBY_FLAVOR}>=0.24,<1 \
		devel/ruby-log4r,${MODRUBY_FLAVOR}=1.1.10 \
		devel/ruby-puppet_forge,${MODRUBY_FLAVOR}>=2.2.8,<3

CONFIGURE_STYLE =	ruby gem

.include <bsd.port.mk>
