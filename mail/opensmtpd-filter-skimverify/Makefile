COMMENT =		spf and dkim verify integration for OpenSMTPD

GH_ACCOUNT =		KrugerHeavyIndustries
GH_PROJECT =		opensmtpd-filter-skimverify
GH_COMMIT =		ed5ef8230f514b7ace5647e2b343ba5e8e43f34a
DISTNAME=		opensmtpd-filter-skimverify-0.0.0.${GH_COMMIT}

CATEGORIES =		mail

MAINTAINER =		Chris Kruger <montdidier@noreply.github.com>

# Unlicense/MIT
PERMIT_PACKAGE =	Yes

WANTLIB +=		${MODCARGO_WANTLIB}

MODULES =		devel/cargo
#BUILD_DEPENDS=		mail/opensmtpd-filter

CONFIGURE_STYLE =	cargo

SEPARATE_BUILD =	Yes

MODCARGO_RUSTFLAGS =	-C debuginfo=0

RELEASE_DIR =		${MODCARGO_TARGET_DIR}/release

do-install:
	${INSTALL_PROGRAM_DIR} ${PREFIX}/libexec/smtpd
	${INSTALL_PROGRAM} ${RELEASE_DIR}/filter-skimverify ${PREFIX}/libexec/smtpd/
	${INSTALL_MAN} ${WRKSRC}/filter-skimverify.8 ${PREFIX}/man/man8/

.include "crates.inc"

.include <bsd.port.mk>
