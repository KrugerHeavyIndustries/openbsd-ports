# $OpenBSD: Makefile,v 1.6 2012/04/28 10:05:30 montdidier Exp $

COMMENT =		Amazon S3 command line tool

VERSION=		0.5.2
DISTNAME =		${VERSION}
EXTRACT_SUFX=
PKGNAME=		s3tools-${VERSION}
WRKDIST= 	${WRKDIR}/KrugerHeavyIndustries-s3tools-*

CATEGORIES =		net
HOMEPAGE =		http://github.com/KrugerHeavyIndustries/s3tools
MAINTAINER =		Chris Kruger <chris.kruger@krugerheavyindustries.com>

# LGPLv3
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_FTP =	Yes

MASTER_SITES =	https://github.com/KrugerHeavyIndustries/s3tools/tarball/

AUTOCONF_VERSION=	2.69
AUTOMAKE_VERSION=	1.12
CONFIGURE_STYLE=	gnu
BUILD_DEPENDS+=		${MODGNU_AUTOCONF_DEPENDS} \
			${MODGNU_AUTOMAKE_DEPENDS}

CONFIGURE_ENV=		CPPFLAGS="-I${LOCALBASE}/include" \
						LDFLAGS="-L${LOCALBASE}/lib"

pre-configure:
	@cd ${WRKSRC} && ${SETENV} ${CONFIGURE_ENV} \
		AUTOCONF_VERSION=${AUTOCONF_VERSION} \
		AUTOMAKE_VERSION=${AUTOMAKE_VERSION} autoreconf --force --install
		
#		AUTOCONF_VERSION=${AUTOCONF_VERSION} ./autogen.sh

.include <bsd.port.mk>
