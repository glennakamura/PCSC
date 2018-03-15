# Process this file with automake to create Makefile.in.

SUBDIRS = . example

man_MANS = pcscd.8
man_in = pcscd.8.in reader.conf.5.in

EXTRA_DIST = $(man_in) doxygen.conf.in formaticc.1 \
	org.debian.pcsc-lite.policy

doxygen:
	rm -fr api ; cd .. ; doxygen doc/doxygen.conf
#	cp doxygen.css api/

if ENABLE_POLKIT
install-data-hook:
	$(MKDIR_P) $(DESTDIR)/$(POLICY_DIR)
	$(INSTALL_DATA) $(srcdir)/org.debian.pcsc-lite.policy $(DESTDIR)/$(POLICY_DIR)

uninstall-hook:
	rm $(DESTDIR)/$(POLICY_DIR)/org.debian.pcsc-lite.policy
endif
