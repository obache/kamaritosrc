# $NetBSD: Makefile,v 1.5 2021/05/28 07:34:36 fcambus Exp $

DISTNAME=	schismtracker-20210525
CATEGORIES=	audio
MASTER_SITES=	${MASTER_SITE_GITHUB:=schismtracker/}
GITHUB_TAG=	${PKGVERSION_NOREV}

MAINTAINER=	fstd.lkml@gmail.com
HOMEPAGE=	http://schismtracker.org/
COMMENT=	Clone of the good old Impulse Tracker
LICENSE=	gnu-gpl-v2

USE_TOOLS+=	autoreconf automake autoconf
MAKE_JOBS_SAFE=	no
GNU_CONFIGURE=	yes

PYTHON_FOR_BUILD_ONLY=	tool

pre-configure:
	cd ${WRKSRC} && autoreconf -i

.include "../../devel/SDL/buildlink3.mk"
.include "../../lang/python/pyversion.mk"
.include "../../mk/bsd.pkg.mk"
