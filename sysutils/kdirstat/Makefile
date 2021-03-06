# Created by: Stefan Jahn <stefan.jahn@nemesis-sektor.de>
# $FreeBSD$

PORTNAME=	kdirstat
PORTVERSION=	3.1.3
PORTREVISION=	1
CATEGORIES=	sysutils kde
MASTER_SITES=	https://bitbucket.org/jeromerobert/k4dirstat/get/
DISTNAME=	k4dirstat-${PORTVERSION}

MAINTAINER=	danilo@FreeBSD.org
COMMENT=	KDE utility that sums up disk usage for directory trees

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/COPYING

USES=		cmake cpe desktop-file-utils gettext-tools kde:5 qt:5 tar:bzip2

WRKSRC=		${WRKDIR}/jeromerobert-k4dirstat-fcf698417d42

CPE_VENDOR=	kdirstat_project
USE_KDE=	auth codecs completion config configwidgets coreaddons doctools \
		i18n iconthemes jobwidgets kio service widgetsaddons xmlgui
USE_QT=		buildtools core gui dbus network qmake widgets xml

post-patch:
	@${REINPLACE_CMD} -e \
		'/^Categories/s|=.*|=Qt;KDE;Utility;|' \
		${WRKSRC}/src/k4dirstat.desktop
	@${REINPLACE_CMD} -e \
		's|<sys/errno.h>|<errno.h>|' \
		${WRKSRC}/src/kdirreadjob.cpp

post-install:
	@${LN} -sf k4dirstat ${STAGEDIR}${PREFIX}/bin/kdirstat

.include <bsd.port.mk>
