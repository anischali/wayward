AC_INIT([wayward], [0.0.1])
LT_INIT
AC_CONFIG_MACRO_DIRS([m4])
AM_INIT_AUTOMAKE([subdir-objects])

dnl Trouver le compilateur C approprie
AC_LANG(C)
AC_PROG_CC

AC_HEADER_STDC

PKG_CHECK_MODULES([cairo], [cairo])
AC_CHECK_DECLS([cairo_create], [], [], [#include <cairo/cairo.h>])

PKG_CHECK_MODULES([glib], [glib-2.0])


PKG_CHECK_MODULES([libweston], [libweston-9])
PKG_CHECK_MODULES([libweston_desktop], [libweston-desktop-9])


PKG_CHECK_MODULES([pixman], [pixman-1])

PKG_CHECK_MODULES([libwayland_client], [wayland-client])
PKG_CHECK_MODULES([libwayland_protocols], [wayland-protocols])
PKG_CHECK_MODULES([libwayland_cursor], [wayland-cursor])
PKG_CHECK_MODULES([libwayland_server], [wayland-server])

PKG_CHECK_MODULES([xkbcommon], [xkbcommon])

PKG_CHECK_MODULES([alsa], [alsa])

PKG_CHECK_MODULES([libjpeg], [libjpeg])

PKG_CHECK_MODULES([libpng], [libpng])

PKG_CHECK_MODULES([libdrm], [libdrm])

PKG_CHECK_MODULES([gdk_pixbuf], [gdk-pixbuf-2.0])

PKG_CHECK_MODULES([libgbm], [gbm])

PKG_CHECK_MODULES([librsvg], [librsvg-2.0])


AC_CONFIG_HEADERS([config.h:config.h.in])

# Check whether exec_prefix=/usr:
AS_CASE([$exec_prefix:$prefix],
[NONE:NONE | NONE:/usr | /usr:*],
  [AC_MSG_NOTICE([Default --exec-prefix detected.])
   AS_CASE([$bindir],  ['${exec_prefix}/bin'],  [bindir=/bin;   AC_MSG_NOTICE([  --bindir defaults to /bin])  ])
   AS_CASE([$sbindir], ['${exec_prefix}/sbin'], [sbindir=/sbin; AC_MSG_NOTICE([  --sbindir defaults to /sbin])])
   AS_CASE([$libdir],  ['${exec_prefix}/lib'],  [libdir=/lib;   AC_MSG_NOTICE([  --libdir defaults to /lib])  ])
  ]
)




echo "	***	Configuring for ... $host	***"

AC_OUTPUT([Makefile] [source/source/Makefile] [source/shared/Makefile])