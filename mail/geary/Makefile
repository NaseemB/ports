# $OpenBSD: Makefile,v 1.52 2019/04/28 07:38:48 landry Exp $

COMMENT =	lightweight mail user agent

GNOME_PROJECT =	geary
GNOME_VERSION =	3.32.1

MAINTAINER =	Landry Breuil <landry@openbsd.org>
CATEGORIES =	mail

# LGPLv2.1
PERMIT_PACKAGE_CDROM =	Yes

HOMEPAGE =	https://wiki.gnome.org/Apps/Geary
MODULES =	devel/meson devel/dconf x11/gnome

MODGNOME_TOOLS += desktop-file-utils gobject-introspection
MODGNOME_TOOLS += gtk-update-icon-cache vala yelp

CONFIGURE_ARGS =-Dlibunwind_optional=true \
		-Diso_639_xml=${LOCALBASE}/share/xml/iso-codes/iso_639.xml \
		-Diso_3166_xml=${LOCALBASE}/share/xml/iso-codes/iso_3166.xml

RUN_DEPENDS =	devel/iso-codes
BUILD_DEPENDS =	devel/iso-codes
LIB_DEPENDS =	mail/gmime \
		net/telepathy/folks \
		x11/gnome/online-accounts \
		security/p11-kit \
		databases/sqlite3 \
		www/webkitgtk4 \
		audio/libcanberra \
		devel/libnotify \
		devel/libgee \
		textproc/enchant2

WANTLIB += atk-1.0 c cairo cairo-gobject canberra enchant-2 folks goa-1.0 gck-1
WANTLIB += gcr-base-3 gdk-3 gdk_pixbuf-2.0 gee-0.8 gio-2.0
WANTLIB += glib-2.0 gmime-2.6 gobject-2.0 json-glib-1.0
WANTLIB += gtk-3 intl javascriptcoregtk-4.0 m notify p11-kit pango-1.0
WANTLIB += pangocairo-1.0 secret-1 soup-2.4 sqlite3 webkit2gtk-4.0
WANTLIB += xml2

.include <bsd.port.mk>
