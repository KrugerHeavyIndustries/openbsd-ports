# $OpenBSD: Makefile,v 1.6 2012/04/28 10:05:30 rpointel Exp $

COMMENT =		cURLpp is a C++ wrapper for libcURL

DISTNAME =		curlpp-0.7.3
EXTRACT_SUFX=		.tar.gz

CATEGORIES =		devel
HOMEPAGE =		http://code.google.com/p/curlpp
MAINTAINER =		Chris Kruger <chris.kruger@krugerheavyindustries.com>

SHARED_LIBS +=		curlpp 0.2
SHARED_LIBS += 		utilspp 0.0

# LGPLv3
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_CDROM =Yes
PERMIT_DISTFILES_FTP =	Yes

WANT_LIB= 		boost curl

MASTER_SITES =	http://curlpp.googlecode.com/files/

CONFIGURE_STYLE=	gnu
CONFIGURE_ARGS+=	${CONFIGURE_SHARED}
CONFIGURE_ENV =		CPPFLAGS="-I${LOCALBASE}/include -fPIC" \
			LDFLAGS="-L${LOCALBASE}/lib" 

BUILD_DEPENDS= 		devel/boost

.include <bsd.port.mk>
