# Noiz2sa makefile(MinGW 2.0.0)
# $Id: Makefile,v 1.4 2003/08/10 09:00:05 kenta Exp $

NAME   = noiz2sa
O      = o
RM     = rm -f
CC     ?= gcc
CXX    ?= g++

PROG        = $(NAME)

DEFAULT_CFLAGS = `sdl2-config --cflags`
LDFLAGS        = `sdl2-config --libs` -L. -L./bulletml/bin/Release -lSDL2_mixer -lbulletml -lstdc++

MORE_CFLAGS = -O3

CFLAGS  = $(DEFAULT_CFLAGS) $(MORE_CFLAGS)
CPPFLAGS  = $(DEFAULT_CFLAGS) $(MORE_CFLAGS) -I./bulletml/ -I./bulletml/include/

OBJS =	$(NAME).$(O) ship.$(O) shot.$(O) frag.$(O) bonus.$(O) \
	foe.$(O) foecommand.$(O) barragemanager.$(O) attractmanager.$(O) \
	background.$(O) letterrender.$(O) \
	screen.$(O) clrtbl.$(O) vector.$(O) degutil.$(O) rand.$(O) soundmanager.$(O)

all: $(PROG)

ifeq ($(OS),Windows_NT)
LDFLAGS += -lmingw32 -lmingwex -mwindows
OBJS += $(NAME)_res.$(O)

$(NAME)_res.o: $(NAME).rc
	windres -i $(NAME).rc -o $(NAME)_res.o
else
LDFLAGS += -lpthread -lm
endif

$(PROG): $(OBJS)
	$(CC) $(CFLAGS) -o $(PROG) $(OBJS) $(LDFLAGS)

clean:
	$(RM) $(PROG) *.$(O)
