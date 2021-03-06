# $OpenBSD: Makefile,v 1.26 2018/11/24 11:27:49 giovanni Exp $

COMMENT-main=		extras for smtpd
COMMENT-mysql=		mysql based smtpd table support
COMMENT-pgsql=		postgresql based smtpd table support
COMMENT-python=		extras with python bindings for smtpd
COMMENT-redis=		redis based smtpd table support

V=			6.4.0
DISTNAME=		opensmtpd-extras-${V}
PKGNAME-main=		${DISTNAME}
PKGNAME-mysql=		opensmtpd-extras-mysql-${V}
PKGNAME-pgsql=		opensmtpd-extras-pgsql-${V}
PKGNAME-python=		opensmtpd-extras-python-${V}
PKGNAME-redis=		opensmtpd-extras-redis-${V}
EPOCH=			0

CATEGORIES=		mail

HOMEPAGE=		https://www.opensmtpd.org/

MAINTAINER=		Giovanni Bechis <giovanni@openbsd.org>, \
			Joerg Jung <jung@openbsd.org>

MULTI_PACKAGES=		-main -mysql -pgsql -python -redis

# BSD
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB=		c crypto event m pthread ssl sqlite3 z
WANTLIB-mysql=		c crypto event ssl m pthread ${COMPILER_LIBCXX} mysqlclient
WANTLIB-pgsql=		c crypto event ssl pq
WANTLIB-python=		c crypto event ssl m util pthread ${MODPY_WANTLIB}
WANTLIB-redis=		c crypto event ssl hiredis

COMPILER =		base-clang ports-gcc base-gcc

MASTER_SITES=		${HOMEPAGE}archives/

MODULES=		lang/python

LIB_DEPENDS-main=	databases/sqlite3
LIB_DEPENDS-mysql=	databases/mariadb,-main
LIB_DEPENDS-pgsql=	databases/postgresql,-main
LIB_DEPENDS-python=	${MODPY_LIB_DEPENDS}
LIB_DEPENDS-redis=	databases/libhiredis
RUN_DEPENDS-python=	${MODPY_RUN_DEPENDS}

CONFIGURE_STYLE=	gnu
CONFIGURE_ARGS=		--mandir=${PREFIX}/man \
			--libexecdir=${PREFIX}/libexec \
			--sysconfdir=${SYSCONFDIR}/mail \
			--with-cppflags="${CFLAGS} -I${PREFIX}/include \
			    -I${PREFIX}/include/postgresql" \
			--with-python-type=python${MODPY_VERSION} \
			--with-queue-null \
			--with-queue-python \
			--with-queue-ram \
			--with-queue-stub \
			--with-scheduler-python \
			--with-scheduler-ram \
			--with-scheduler-stub \
			--with-table-ldap \
			--with-table-mysql \
			--with-table-passwd \
			--with-table-postgres \
			--with-table-python \
			--with-table-redis \
			--with-table-socketmap \
			--with-table-sqlite \
			--with-table-stub

.include <bsd.port.mk>
