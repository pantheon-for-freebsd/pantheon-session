PORTNAME=	pantheon-session
DISTVERSION=	6.0.0
CATEGORIES=	sysutils

MAINTAINER=	inucat@proton.me
COMMENT=	Unofficial port of elementary OS settings daemon
WWW=		https://github.com/elementary/session-settings/

LICENSE=	GPLv3

BUILD_DEPENDS=	\
	gnome-keyring-daemon:security/gnome-keyring \
	orca:accessibility/orca

USES=vala meson ninja pkgconfig
MESON_ARGS=		--prefix=${PREFIX}
MESON_BUILD_DIR=	build
USE_GITHUB=		yes
GH_ACCOUNT=		elementary
GH_PROJECT=		session-settings

do-build:
	cd ${WRKSRC} && meson setup build
	cd ${WRKSRC}/build && ninja

do-stage:
	cd ${WRKSRC}/build && DESTDIR=${WRKSRC}/../stage ninja install

.include <bsd.port.mk>
