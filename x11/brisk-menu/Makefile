# Created by: Eric Turgeon <ericbsd@FreeBSD.org>
# $FreeBSD$

PORTNAME=	brisk-menu
DISTVERSIONPREFIX=	v
DISTVERSION=	0.5.1
PORTREVISION=	2
CATEGORIES=	x11

MAINTAINER=	ericbsd@FreeBSD.org
COMMENT=	Brisk Menu is an efficient menu for the MATE Desktop

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/LICENSE

LIB_DEPENDS=	libnotify.so:devel/libnotify

USES=		compiler:c11 gnome mate meson ninja pkgconfig gettext
MESON_ARGS=	--sysconfdir=${PREFIX}/etc

USE_GITHUB=	yes
GH_ACCOUNT=	GhostBSD

USE_GNOME=	gtk30
USE_MATE=	menus panel
GLIB_SCHEMAS=	com.solus-project.brisk-menu.gschema.xml

.if exists(/usr/bin/ld.lld)
LDFLAGS+=	-fuse-ld=lld
.else
USE_BINUTILS=	yes
LDFLAGS+=	-B${LOCALBASE}/bin
.endif

.include <bsd.port.mk>
