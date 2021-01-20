# $OpenBSD: Makefile,v 1.9 2020/09/02 10:50:36 sthen Exp $

FIX_EXTRACT_PERMISSIONS = Yes

COMMENT =		bitwarden_rs alt Bitwarden backend

GH_ACCOUNT =		dani-garcia
GH_PROJECT =		bitwarden_rs
GH_TAGNAME =		async
REVISION =		0

PKGNAME	=		bitwarden_rs-1.17.0

CATEGORIES =		security

MAINTAINER =		Chris Kruger <openbsd@krugerheavyindustries.com>

# BSD
PERMIT_PACKAGE =	Yes

WANTLIB +=		ssl

MODULES =		devel/cargo
BUILD_DEPENDS =		lang/rust>=1.30
LIB_DEPENDS=		

SEPARATE_BUILD =	Yes
NO_TEST =		Yes

CONFIGURE_STYLE =	cargo

DISTFILES +=		${DISTNAME}${EXTRACT_SUFX}

MODCARGO_FEATURES = 	postgresql
VENDORTAR = https://f001.backblazeb2.com/file/openbsd-artifacts/bitwarden_rs-1.17.0-vendor.tar.gz

RELEASE_DIR =		${MODCARGO_TARGET_DIR}/release

post-extract: 
	cd ${WRKSRC} && curl ${VENDORTAR} | tar -zxv

do-install:
	${INSTALL_PROGRAM} ${RELEASE_DIR}/bitwarden_rs ${PREFIX}/sbin/

.include <bsd.port.mk>
