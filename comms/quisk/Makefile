# Created by: Stephen Hurd <shurd@FreeBSD.org>
# $FreeBSD: head/comms/quisk/Makefile 412716 2016-04-08 04:17:36Z shurd $

PORTNAME=	quisk
PORTVERSION=	4.1.3
CATEGORIES=	comms hamradio
MASTER_SITES=	http://james.ahlstrom.name/quisk/ \
		LOCAL/db

MAINTAINER=	hamradio@FreeBSD.org
COMMENT=	Software Defined Radio (SDR)

LICENSE=	GPLv2

LIB_DEPENDS=	libfftw3.so:math/fftw3 \
		libportaudio.so:audio/portaudio \
		libasound.so:audio/alsa-lib \
		libpulse.so:audio/pulseaudio

USES=		python
USE_PYTHON=	distutils autoplist
USE_WX=		3.0+
WX_COMPS=	python

post-extract:
	${RM} ${WRKSRC}/_quisk.so ${WRKSRC}/sdriqpkg/sdriq.so

post-patch:
	${REINPLACE_CMD} -e 's|%%LOCALBASE%%|${LOCALBASE}|g' ${WRKSRC}/setup.py

.include <bsd.port.mk>
