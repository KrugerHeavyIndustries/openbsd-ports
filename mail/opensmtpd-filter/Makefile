COMMENT =		line oriented search tool using Rust's regex library

GH_ACCOUNT =		KrugerHeavyIndustries
GH_PROJECT =		opensmtpd-filter_rs
GH_COMMIT =		6df7bf2c5f9169cc6e09286014aee81ffacf4fab
DISTNAME=		opensmtpd-filter-0.1.0.${GH_COMMIT}

CATEGORIES =		mail

MAINTAINER =		Chris Kruger <montdidier@noreply.github.com>

# Unlicense/MIT
PERMIT_PACKAGE =	Yes

WANTLIB +=		${MODCARGO_WANTLIB}

MODULES =		devel/cargo

CONFIGURE_STYLE =	cargo

SEPARATE_BUILD =	Yes

MODCARGO_RUSTFLAGS =	-C debuginfo=0

RELEASE_DIR =		${MODCARGO_TARGET_DIR}/release

.include "crates.inc"

.include <bsd.port.mk>
