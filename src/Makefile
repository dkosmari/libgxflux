LIBRARY = 1
TARGET = libgxflux.a

OBJS = gfx.o gfx_tex.o gfx_color.o gfx_con.o gfx_con_font.o
HEADERS = gfx.h gfx_types.h gfx_tex.h gfx_color.h gfx_con.h gfx_con_esc.h

include ../common.mk

ifeq ($(GAMECUBE),1)
INSTALLLIB = $(DESTDIR)$(DEVKITPRO)/libogc/lib/cube
else
INSTALLLIB = $(DESTDIR)$(DEVKITPRO)/libogc/lib/wii
endif

INSTALLINCLUDE = $(DESTDIR)$(DEVKITPRO)/libogc/include/gxflux

install: all
	@echo "  INSTALL   $(INSTALLLIB)"
	@install -Dm 644 $(TARGET) $(INSTALLLIB)
	@mkdir -p $(INSTALLINCLUDE)
	@install -m 644 $(HEADERS) $(INSTALLINCLUDE)

install-all:
	@$(MAKE) --no-print-directory clean
	@$(MAKE) --no-print-directory install
	@$(MAKE) --no-print-directory clean
	@$(MAKE) --no-print-directory GAMECUBE=1 install
	@$(MAKE) --no-print-directory GAMECUBE=1 clean


.PHONY: install

