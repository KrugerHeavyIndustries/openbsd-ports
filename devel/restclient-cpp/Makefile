# $OpenBSD: Makefile $

COMMENT =		C++ client for making HTTP/REST requests

GH_ACCOUNT =	        mrtazz
GH_PROJECT =		restclient-cpp
GH_TAGNAME =		0.5.2
PKGNAME = 		${DISTNAME:L}

CATEGORIES =		devel
HOMEPAGE =		http://code.mrtazz.com/restclient-cpp
MAINTAINER =		Chris Kruger <openbsd@krugerheavyindustries.com>

SHARED_LIBS +=		restclient-cpp 0.0

#SEPARATE_BUILD = Yes

# LGPLv3
PERMIT_PACKAGE =	Yes
PERMIT_DISTFILES =	Yes

AUTOCONF_VERSION=	2.69
AUTOMAKE_VERSION=	1.15
CONFIGURE_STYLE=	gnu
BUILD_DEPENDS+=		${MODGNU_AUTOCONF_DEPENDS} \
			${MODGNU_AUTOMAKE_DEPENDS} \
			net/curl

CONFIGURE_ARGS+=	${CONFIGURE_SHARED}
CONFIGURE_ENV =		CXXFLAGS="-I${LOCALBASE}/include -fPIC" \
			LDFLAGS="-L${LOCALBASE}/lib" 

WANTLIB += 		c crypto m ssl c++ z

USE_LIBTOOL=		gnu

pre-configure:
	@cd ${WRKSRC} && ${SETENV} ${CONFIGURE_ENV} \
		AUTOCONF_VERSION=${AUTOCONF_VERSION} \
		AUTOMAKE_VERSION=${AUTOMAKE_VERSION} autoreconf --force --install
.include <bsd.port.mk>
