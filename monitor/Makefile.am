
AM_CFLAGS = -DPKGDATADIR=\"$(pkgdatadir)\" \
	-DPACKAGE_DATA_DIR=\""$(pkgdatadir)"\" \
	-DSEAFILE_SERVER \
	-I$(top_srcdir)/include \
	-I$(top_srcdir)/lib \
	-I$(top_builddir)/lib \
	-I$(top_srcdir)/common \
	@CCNET_CFLAGS@ \
	@SEARPC_CFLAGS@ \
	@GLIB2_CFLAGS@ \
	@MYSQL_CFLAGS@ \
	@ZDB_CFLAGS@ \
	@MSVC_CFLAGS@ \
	@CURL_CFLAGS@ \
	-Wall

bin_PROGRAMS = seaf-mon

noinst_HEADERS = \
	seafile-session.h \
	repo-mgr.h \
	scheduler.h

seaf_mon_SOURCES = \
	seaf-mon.c \
	seafile-session.c \
	repo-mgr.c \
	scheduler.c \
	monitor-rpc.c \
	../common/seaf-db.c \
	../common/bitfield.c \
	../common/branch-mgr.c \
	../common/fs-mgr.c \
	../common/block-mgr.c \
	../common/block-backend.c \
	../common/block-backend-fs.c \
	../common/block-backend-ceph.c \
	../common/commit-mgr.c \
	../common/avl/avl.c \
	../common/log.c \
	../common/seaf-utils.c \
	../common/obj-store.c \
	../common/obj-backend-fs.c \
	../common/obj-backend-riak.c \
	../common/riak-http-client.c \
	../common/seafile-crypt.c \
	../common/mq-mgr.c

seaf_mon_LDADD = @CCNET_LIBS@ \
	$(top_builddir)/common/cdc/libcdc.la \
	$(top_builddir)/lib/libseafile_common.la \
	@GLIB2_LIBS@  @GOBJECT_LIBS@ -lssl @LIB_RT@ @LIB_UUID@ -lsqlite3 -levent \
	@MYSQL_LIBS@  @SEARPC_LIBS@ @ZDB_LIBS@ @RADOS_LIBS@ @CURL_LIBS@ ${LIB_WS32}

seaf_mon_LDFLAGS = @STATIC_COMPILE@ @SERVER_PKG_RPATH@
