
MANPAGE_GEN_FILES=manpage.template docgen default.cfg.template extra.cfg.template

docdir=$(prefix)/share/doc/@PACKAGE@

if HAVE_PYTHON

man_MANS=chocolate-doom.6      \
         chocolate-server.6    \
         chocolate-setup.6     \
         default.cfg.5         \
         $(PACKAGE).cfg.5

nodist_doc_DATA=INSTALL

chocolate-doom.6: ../src $(MANPAGE_GEN_FILES)
	./docgen -m manpage.template ../src > $@

default.cfg.5: ../src default.cfg.template
	./docgen -m default.cfg.template -c default.cfg ../src > $@

$(PACKAGE).cfg.5: ../src extra.cfg.template
	./docgen -m extra.cfg.template -c chocolate-doom.cfg ../src > $@

INSTALL: INSTALL.template
	./simplecpp -DPRECOMPILED < INSTALL.template > $@

endif

EXTRA_DIST = $(man_MANS) $(MANPAGE_GEN_FILES)        \
             wikipages                               \
             CMDLINE.template                        \
             INSTALL.template                        \
             simplecpp

