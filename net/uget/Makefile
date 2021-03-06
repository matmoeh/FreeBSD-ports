# Created by: Olivier Duchateau
# $FreeBSD$

PORTNAME=	uget
PORTVERSION=	2.0.8
PORTREVISION=	1
CATEGORIES=	net
MASTER_SITES=	SF/urlget/${PORTNAME}%20%28stable%29/${PORTVERSION}

MAINTAINER=	olivierd@FreeBSD.org
COMMENT=	Download manager application

LICENSE=	LGPL21
LICENSE_FILE=	${WRKSRC}/COPYING

BUILD_DEPENDS=	curl-config:ftp/curl
LIB_DEPENDS=	libnotify.so:devel/libnotify \
	libgcrypt.so:security/libgcrypt \
	libgnutls.so:security/gnutls
RUN_DEPENDS=	aria2c:www/aria2

USES=	compiler:c11 gettext-tools gmake pkgconfig
GNU_CONFIGURE=	yes
USE_GNOME=	glib20 gtk30 intltool intlhack
INSTALLS_ICONS=	yes
INSTALL_TARGET=	install-strip

# Avoid warning, with redefinition of typedef (C11 feature)
CFLAGS+=	-Wno-typedef-redefinition

CONFIGURE_ARGS=--enable-appindicator=no \
	--disable-pwmd \
	--enable-unix-socket \
	--with-gnutls=yes

OPTIONS_DEFINE=	GSTREAMER NLS
OPTIONS_DEFAULT=	GSTREAMER
GSTREAMER_USE=	gstreamer1=yes
GSTREAMER_CONFIGURE_ENABLE=	gstreamer
NLS_USES=	gettext-runtime
NLS_CONFIGURE_ENABLE=	nls
OPTIONS_SUB=	yes

.include <bsd.port.mk>
