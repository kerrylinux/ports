# $FreeBSD$

PORTNAME=	restic
DISTVERSIONPREFIX=	v
DISTVERSION=	0.9.3
CATEGORIES=	sysutils

MAINTAINER=	gregf@hugops.pw
COMMENT=	Fast, secure, efficient backup program

LICENSE=	BSD2CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

USES=		go
USE_GITHUB=	yes

GO_PKGNAME=	github.com/${GH_ACCOUNT}/${PORTNAME}
GO_TARGET=	${GO_PKGNAME}/cmd/${PORTNAME}

PLIST_SUB=	PORTNAME=${PORTNAME}

post-install:
	${INSTALL_MAN} ${WRKSRC}/doc/man/* ${STAGEDIR}${MANPREFIX}/man/man1
	${INSTALL} -d ${STAGEDIR}${PREFIX}/etc/bash_completion.d/
	${INSTALL_SCRIPT} ${WRKSRC}/doc/bash-completion.sh \
		${STAGEDIR}${PREFIX}/etc/bash_completion.d/${PORTNAME}.sh
	${INSTALL} -d ${STAGEDIR}${PREFIX}/share/zsh/site-functions/
	${INSTALL_DATA} ${WRKSRC}/doc/zsh-completion.zsh \
		${STAGEDIR}${PREFIX}/share/zsh/site-functions/_${PORTNAME}

.include <bsd.port.mk>
