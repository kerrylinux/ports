# $FreeBSD$

PORTNAME=	pdk
PORTVERSION=	1.9.0
CATEGORIES=	devel rubygems
MASTER_SITES=	RG

MAINTAINER=	puppet@FreeBSD.org
COMMENT=	CLI for development of Puppet modules

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=    rubygem-bundler>=1.15:sysutils/rubygem-bundler \
		rubygem-childprocess>=0.7.1:devel/rubygem-childprocess \
		rubygem-cri>=2.10.1:devel/rubygem-cri \
		rubygem-deep_merge>=1.1:devel/rubygem-deep_merge \
		rubygem-diff-lcs>=1.3:textproc/rubygem-diff-lcs \
		rubygem-gettext-setup>=0.24:devel/rubygem-gettext-setup \
		rubygem-json-schema>=2.8.0:devel/rubygem-json-schema \
		rubygem-hitimes>=1.3.0:devel/rubygem-hitimes \
		rubygem-json_pure>=2.1.0:devel/rubygem-json_pure \
		rubygem-minitar>=0.6.1:archivers/rubygem-minitar \
		rubygem-net-ssh>=4.2.0:security/rubygem-net-ssh \
		rubygem-pathspec>=0.2.1:devel/rubygem-pathspec \
		rubygem-tty-prompt>=0.13.1:devel/rubygem-tty-prompt \
		rubygem-tty-spinner>=0.5.0:devel/rubygem-tty-spinner \
		rubygem-tty-which>=0.3.0:devel/rubygem-tty-which

USES=		gem
USE_RUBY=	yes

PLIST_FILES=	bin/pdk

.include <bsd.port.mk>
