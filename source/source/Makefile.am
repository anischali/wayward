bin_PROGRAMS = wayward wayward-terminal shell_helper.so


EXTRA_CCFLAGS=-std=c11 -pthread \
    -I. \
    -I.. \
    -I../shared/ \
    -Igen-protocol \
    $(cairo_CFLAGS) \
    $(glib_CFLAGS) \
    $(libweston_CFLAGS) \
    $(pixman_CFLAGS) \
    $(libpng_CFLAGS) \
    $(gdk_pixbuf_CFLAGS) \
    $(libweston_desktop_CFLAGS) \
    $(libgbm_CFLAGS)

    


EXTRA_LIBS= $(libwayland_client_LIBS) $(libgbm_LIBS) $(libpng_LIBS) $(gdk_pixbuf_LIBS) $(libweston_desktop_LIBS) -lutil \
   $(libwayland_cursor_LIBS) $(pixman_LIBS) $(libweston_LIBS) $(cairo_LIBS) $(glib_LIBS) $(xkbcommon_LIBS) $(alsa_LIBS) $(libjpeg_LIBS) -lm -lrt

CLIENT_SRC=\
    terminal.c

WINDOW_SRC=\
    window.c				\
    ../shared/file-util.c \
    ../shared/image-loader.c \
    ../shared/cairo-util.c \
    ../shared/xalloc.c \
    ../shared/option-parser.c \
    ../shared/frame.c \
    ../shared/os-compatibility.c \
    ../shared/config-parser.c \
    gen-protocol/xdg-shell-protocol.c \
    gen-protocol/viewporter-protocol.c \
    gen-protocol/pointer-constraints-unstable-v1-protocol.c \
    gen-protocol/relative-pointer-unstable-v1-protocol.c \
    gen-protocol/text-cursor-position-protocol.c \
    gen-protocol/weston-desktop-shell-code.c \
    gen-protocol/shell-helper-protocol.c

SIMLE_EGL_SRC=\
    simple-egl.c

SIMLE_SHM_SRC=\
    simple-shm.c

WAYWARD_SRC=\
    wayward-shell.c

SHELL_HELPER_SRC=\
    shell-helper.c


wayward_CFLAGS = $(CFLAGS) $(EXTRA_CCFLAGS)

wayward_LDFLAGS = $(LDFLAGS)

wayward_LDADD = $(LDADD) $(EXTRA_LIBS)

wayward_SOURCES = \
    $(WAYWARD_SRC) \
    $(WINDOW_SRC)


wayward_terminal_CFLAGS = $(CFLAGS) $(EXTRA_CCFLAGS)


wayward_terminal_LDFLAGS = $(LDFLAGS)

wayward_terminal_LDADD = $(LDADD) $(EXTRA_LIBS)

wayward_terminal_SOURCES = \
    $(CLIENT_SRC) \
    $(WINDOW_SRC)




shell_helper_so_CFLAGS = $(CFLAGS) $(EXTRA_CCFLAGS) $(libdrm_CFLAGS)

shell_helper_so_LDFLAGS = $(LDFLAGS) -shared -fPIC

shell_helper_so_LDADD = $(LDADD) $(EXTRA_LIBS)

shell_helper_so_SOURCES = \
    gen-protocol/weston-desktop-shell-code.c \
    gen-protocol/shell-helper-protocol.c \
    $(SHELL_HELPER_SRC)


pkgconfigdir = $(libdir)/pkgconfig




distclean-local:
	-rm -rf .deps
	-rm -f Makefile.in
	-rm -f Makefile