# $NetBSD: Makefile,v 1.11 2021/05/24 19:50:11 wiz Exp $

DISTNAME=	CPAN-Mini-1.111016
PKGNAME=	p5-${DISTNAME}
PKGREVISION=	7
CATEGORIES=	devel perl5
MASTER_SITES=	${MASTER_SITE_PERL_CPAN:=CPAN/}

MAINTAINER=	wen@NetBSD.org
HOMEPAGE=	https://metacpan.org/release/CPAN-Mini
COMMENT=	Create a minimal mirror of CPAN
LICENSE=	${PERL5_LICENSE}

DEPENDS+=	p5-File-HomeDir>=0.57:../../devel/p5-File-HomeDir
DEPENDS+=	p5-libwww>=5:../../www/p5-libwww
DEPENDS+=	p5-URI>=1:../../www/p5-URI

PERL5_PACKLIST=		auto/CPAN/Mini/.packlist

.include "../../lang/perl5/module.mk"
.include "../../mk/bsd.pkg.mk"
