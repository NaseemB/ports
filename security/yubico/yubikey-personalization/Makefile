# $OpenBSD: Makefile,v 1.10 2019/04/29 16:27:26 sthen Exp $

COMMENT=	library and tools to program YubiKeys

YK_PROJECT=	yubikey-personalization
DISTNAME=	ykpers-1.19.3

SHARED_LIBS +=	ykpers-1                  0.7 # 20.0

CATEGORIES=	sysutils

MAINTAINER=	Stuart Henderson <sthen@openbsd.org>

WANTLIB += c json-c pthread usb-1.0 yubikey

LIB_DEPENDS=	devel/json-c \
		devel/libusb1>=1.0.9p1 \
		security/yubico/yubico-c

CONFIGURE_STYLE= gnu

.include <bsd.port.mk>
