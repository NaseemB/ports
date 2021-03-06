# $OpenBSD: Makefile,v 1.83 2018/06/29 22:16:10 espie Exp $

COMMENT=	editor for the GConf configuration system

GNOME_PROJECT=	gconf-editor
GNOME_VERSION=	3.0.1
REVISION=	14

CATEGORIES=	devel x11

MAINTAINER=	Jasper Lievisse Adriaanse <jasper@openbsd.org>, \
		Antoine Jacoutot <ajacoutot@openbsd.org>

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB =  X11 Xcomposite Xcursor Xdamage Xext Xfixes Xi Xinerama Xrandr
WANTLIB += Xrender Xtst atk-1.0 atk-bridge-2.0 atspi c cairo
WANTLIB += cairo-gobject dbus-1 dbus-glib-1 epoxy expat ffi fontconfig
WANTLIB += freetype gdk-3 gdk_pixbuf-2.0 gio-2.0 glib-2.0 gmodule-2.0
WANTLIB += gobject-2.0 graphite2 gthread-2.0 gtk-3 harfbuzz iconv intl m
WANTLIB += pango-1.0 pangocairo-1.0 pangoft2-1.0 pcre pixman-1 png
WANTLIB += pthread xcb xcb-render xcb-shm z

MODULES=	x11/gnome \
		devel/gconf2

LIB_DEPENDS=	x11/gtk+3

MODGNOME_TOOLS += desktop-file-utils gtk-update-icon-cache yelp

MODGCONF2_SCHEMAS_DIR=	gconf-editor

CONFIGURE_STYLE=gnu

# the devel/gconf2 MODULE overrides the path to gconftool-2
CONFIGURE_ARGS += --with-gconf-defaults-source="xml:merged:/var/db/gconf/gconf.xml.defaults" \
	--with-gconf-mandatory-source="xml:merged:/var/db/gconf/gconf.xml.mandatory"

.include <bsd.port.mk>
