PROG=	filter-dkim-signer
MAN=	filter-dkim-signer.8
MANDIR=	/usr/local/man/man
BINDIR=	/usr/local/libexec/smtpd

api_srcdir= .
APIDIR= $(.CURDIR)/../../../api
.PATH: $(APIDIR)
.include "$(.CURDIR)/../../../mk/filter.mk"

SRCS+=	filter_dkim_signer.c

.ifdef DEBUG
# e.g. make DEBUG=-ggdb
CFLAGS=		-O0 $(PIPE) $(DEBUG)
.endif

CFLAGS+=	-I${.CURDIR} -I$(APIDIR)

CFLAGS+=	-Wall -Werror -Wno-unused-function -Wno-implicit
LDADD=		-levent -lcrypto -lutil

.include <bsd.prog.mk>
