# Created by: ache
# $FreeBSD$

PORTNAME=	sharutils
PORTVERSION=	4.15.2
PORTREVISION=	2
CATEGORIES=	archivers
MASTER_SITES=	GNU

MAINTAINER=	garga@FreeBSD.org
COMMENT=	Pack, send, and unpack shell archives; synchronize via e-mail

LICENSE=	GPLv3

OPTIONS_DEFINE=	NLS

GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--program-prefix=g --disable-uucode
INSTALL_TARGET=	install install-man
INFO=		sharutils
USES=		charsetfix cpe perl5 tar:xz
USE_PERL5=	build
OPTIONS_SUB=	yes
CPE_VENDOR=	gnu

NLS_USES=	gettext
NLS_CONFIGURE_ON=	--with-libintl-prefix="${LOCALBASE}"
NLS_CONFIGURE_OFF=	--disable-nls

post-patch:
	@${REINPLACE_CMD} -e '/Please include config.h first./ s,^.*$$,#include <config.h>,' \
		${WRKSRC}/lib/unistd.in.h
.for man in shar.1 unshar.1
	@${REINPLACE_CMD} \
		-e 's, SHAR , GSHAR ,' \
		-e 's,Shar,Gshar,' \
		-e 's, shar , gshar ,g' \
		-e 's,^shar ,gshar ,' \
		-e 's, UNSHAR , GUNSHAR ,' \
		-e 's,Unshar,Gunshar,' \
		-e 's,^unshar ,gunshar ,' \
		-e 's,f2shar\\f1,f2gshar\\f1,' \
		-e 's, unshar , gunshar ,g' \
		-e 's,gshar file,shar file,g' \
		-e 's,shar\,,gshar\,,' \
		-e 's,shar(,gshar(,' \
		-e 's,unshar(,gunshar(,' \
		-e 's, shar\$$, gshar,' \
		${WRKSRC}/doc/${man}
.endfor

.include <bsd.port.mk>
