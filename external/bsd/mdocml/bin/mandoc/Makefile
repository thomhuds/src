# $NetBSD: Makefile,v 1.13 2018/08/14 08:53:06 christos Exp $

.include <bsd.own.mk>

PROG=		mandoc

SRCS=	\
eqn_html.c \
eqn_term.c \
html.c \
main.c \
man_html.c \
man_term.c \
mandoc_xr.c \
manpath.c \
mdoc_html.c \
mdoc_markdown.c \
mdoc_term.c \
out.c \
roff_html.c \
roff_term.c \
tbl_html.c \
tbl_term.c \
term.c \
term_ascii.c \
term_ps.c \
term_tab.c \
tree.c

.ifndef HOSTPROG
DPADD+= 	${MDOCMLLIB.mandoc} ${LIBZ}
LDADD+= 	-L${MDOCMLOBJDIR.mandoc} -lmandoc -lz
CPPFLAGS+=	-DUSE_WCHAR
.else
SRCS.libmandoc!=cd ${.PARSEDIR}/../../lib/libmandoc && ${MAKE} -v SRCS

SRCS+=		${SRCS.libmandoc} compat_strtonum.c compat_reallocarray.c
.endif

.include <bsd.prog.mk>
