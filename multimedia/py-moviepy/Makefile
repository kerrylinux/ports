# $FreeBSD$

PORTNAME=	moviepy
PORTVERSION=	0.2.3.5
PORTREVISION=	2
CATEGORIES=	multimedia python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Video editing with Python

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENCE.txt

RUN_DEPENDS=	ffmpeg:multimedia/ffmpeg \
		${PYTHON_PKGNAMEPREFIX}decorator>=4.0.2:devel/py-decorator@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}imageio>=2.1.2:graphics/py-imageio@${PY_FLAVOR} \
		${PYNUMPY} \
		${PYTHON_PKGNAMEPREFIX}tqdm>=4.11.2:misc/py-tqdm@${PY_FLAVOR} \

USES=		python
USE_PYTHON=	autoplist concurrent distutils

NO_ARCH=	yes

OPTIONS_SINGLE=	IMAGEMAGICK
OPTIONS_SINGLE_IMAGEMAGICK=	IMAGEMAGICK6 IMAGEMAGICK7
OPTIONS_DEFAULT=IMAGEMAGICK7
IMAGEMAGICK6_DESC=	Use ImageMagick 6.x as backend
IMAGEMAGICK7_DESC=	Use ImageMagick 7.x as backend
IMAGEMAGICK6_RUN_DEPENDS=	convert:graphics/ImageMagick6
IMAGEMAGICK7_RUN_DEPENDS=	convert:graphics/ImageMagick7

.include <bsd.port.mk>
