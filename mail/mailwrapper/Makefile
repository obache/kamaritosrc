# $NetBSD: Makefile,v 1.29 2019/11/02 16:25:23 rillig Exp $

DISTNAME=	mailwrapper-19990412
PKGREVISION=	4
CATEGORIES=	mail
MASTER_SITES=	${MASTER_SITE_LOCAL}

MAINTAINER=	pkgsrc-users@NetBSD.org
COMMENT=	Wrapper to support arbitrary Mail Transport Agents
LICENSE=	original-bsd

USE_FEATURES+=		cdefs
USE_BSD_MAKEFILE=	yes

WRKSRC=			${WRKDIR}/mailwrapper

EGDIR=			${PREFIX}/share/examples/mailwrapper

MAILWRAPPER_BACKUP_SFX=	.pkgsrc.mailwrapper
FILES_SUBST+=		MAILWRAPPER_BACKUP_SFX=${MAILWRAPPER_BACKUP_SFX:Q}

MAILWRAPPEES=	/usr/bin/mailq						\
		/usr/bin/newaliases	/usr/sbin/newaliases		\
		/usr/sbin/sendmail	/usr/lib/sendmail
FILES_SUBST+=	MAILWRAPPEES=${MAILWRAPPEES:Q}

INSTALLATION_DIRS=	${PKGMANDIR}/cat5 ${PKGMANDIR}/cat8 \
			${PKGMANDIR}/man5 ${PKGMANDIR}/man8 sbin \
			share/examples/mailwrapper

SUBST_CLASSES+=		syscfdir
SUBST_STAGE.syscfdir=	do-configure
SUBST_MESSAGE.syscfdir=	replace hard coded "/etc" with PKG_SYSCONFDIR
SUBST_FILES.syscfdir=	mailer.conf.5 mailwrapper.8 mailwrapper.c
SUBST_SED.syscfdir=	-e "s|/etc/\\(mailer.conf\\)|${PKG_SYSCONFDIR}/\\1|g"

post-install:
	${INSTALL_DATA} ${WRKSRC}/mailer.conf ${DESTDIR}${EGDIR}/mailer.conf.sendmail

.include "../../mk/bsd.pkg.mk"
