# $OpenBSD: Makefile,v 1.6 2012/04/28 10:05:30 rpointel Exp $

COMMENT =		Amazon S3 command line tool

VERSION=			0.01
DISTNAME =		master
EXTRACT_SUFX=
PKGNAME=		s3tools-${VERSION}
WRKDIST= 	${WRKDIR}/KrugerHeavyIndustries-s3tools-*

CATEGORIES =		net
HOMEPAGE =		http://github.com/KrugerHeavyIndustries/s3tools
MAINTAINER =		Chris Kruger <openbsd@krugerheavyindustries.com>

# LGPLv3
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_CDROM =Yes
PERMIT_DISTFILES_FTP =	Yes

WANT_LIB= 	curlpp

MASTER_SITES =	https://github.com/KrugerHeavyIndustries/s3tools/tarball/

AUTOCONF_VERSION=2.69
AUTOMAKE_VERSION=1.12

CONFIGURE_STYLE=	gnu

CONFIGURE_ENV=		CPPFLAGS="-I${LOCALBASE}/include" \
						LDFLAGS="-L${LOCALBASE}/lib"

pre-configure:
	@cd ${WRKSRC} && ${SETENV} ${CONFIGURE_ENV} \
		AUTOCONF_VERSION=${AUTOCONF_VERSION} \
		AUTOMAKE_VERSION=${AUTOMAKE_VERSION} autoreconf --force --install
		
.include <bsd.port.mk>
