# $OpenBSD: Makefile,v 1.6 2023/05/08 21:05:30 montdidier Exp $

COMMENT =		Backblaze B2 command line tool

VERSION=		0.4.8
REVISION=		0
DISTNAME =		blazer-${VERSION}.tar.gz
EXTRACT_SUFX=
PKGNAME=		blazer-${VERSION}
#WRKDIST= 		${WRKDIR}/KrugerHeavyIndustries-blazer-*

CATEGORIES =		net
HOMEPAGE =		http://github.com/KrugerHeavyIndustries/blazer
MAINTAINER =		Chris Kruger <chris.kruger@krugerheavyindustries.com>

# LGPLv3
PERMIT_PACKAGE =	Yes
PERMIT_DISTFILES =	Yes

GH_ACCOUNT=		KrugerHeavyIndustries
GH_PROJECT=		blazer
GH_TAGNAME=		${VERSION}

AUTOCONF_VERSION=	2.69
AUTOMAKE_VERSION=	1.15

CONFIGURE_STYLE=	gnu
BUILD_DEPENDS+=		devel/jansson

CONFIGURE_ENV=		CPPFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib"

MAKE_ENV+= 		AUTOCONF_VERSION=${AUTOCONF_VERSION} \
			AUTOMAKE_VERSION=${AUTOMAKE_VERSION}

LIB_DEPENDS+=		devel/jansson devel/restclient-cpp
WANTLIB+=		c crypto m ssl c++ jansson restclient-cpp

pre-configure:
	@cd ${WRKSRC} && ${SETENV} ${CONFIGURE_ENV} \
	AUTOCONF_VERSION=${AUTOCONF_VERSION} \
	AUTOMAKE_VERSION=${AUTOMAKE_VERSION} \
	autoreconf --force --install

.include <bsd.port.mk>
