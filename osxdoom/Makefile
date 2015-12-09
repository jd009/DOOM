################################################################
#
# $Id:$
#
# $Log:$
#
CC=  gcc  # gcc or g++

#CFLAGS=-g -Wall -DNORMALUNIX -DLINUX # -DUSEASM #JD Removed DLINUX
CFLAGS=-g -Wall -DNORMALUNIX # -DUSEASM 
LDFLAGS=-L/usr/X11R6/lib
LIBS=-lXext -lX11 -lnsl -lm

# subdirectory for objects
OUTPUT_DIR=osx

# not too sophisticated dependency
OBJECTS=				\
		$(OUTPUT_DIR)/doomdef.o		\
		$(OUTPUT_DIR)/doomstat.o		\
		$(OUTPUT_DIR)/dstrings.o		\
		$(OUTPUT_DIR)/i_system.o		\
		$(OUTPUT_DIR)/i_sound.o		\
		$(OUTPUT_DIR)/i_video.o		\
		$(OUTPUT_DIR)/i_net.o			\
		$(OUTPUT_DIR)/tables.o			\
		$(OUTPUT_DIR)/f_finale.o		\
		$(OUTPUT_DIR)/f_wipe.o 		\
		$(OUTPUT_DIR)/d_main.o			\
		$(OUTPUT_DIR)/d_net.o			\
		$(OUTPUT_DIR)/d_items.o		\
		$(OUTPUT_DIR)/g_game.o			\
		$(OUTPUT_DIR)/m_menu.o			\
		$(OUTPUT_DIR)/m_misc.o			\
		$(OUTPUT_DIR)/m_argv.o  		\
		$(OUTPUT_DIR)/m_bbox.o			\
		$(OUTPUT_DIR)/m_fixed.o		\
		$(OUTPUT_DIR)/m_swap.o			\
		$(OUTPUT_DIR)/m_cheat.o		\
		$(OUTPUT_DIR)/m_random.o		\
		$(OUTPUT_DIR)/am_map.o			\
		$(OUTPUT_DIR)/p_ceilng.o		\
		$(OUTPUT_DIR)/p_doors.o		\
		$(OUTPUT_DIR)/p_enemy.o		\
		$(OUTPUT_DIR)/p_floor.o		\
		$(OUTPUT_DIR)/p_inter.o		\
		$(OUTPUT_DIR)/p_lights.o		\
		$(OUTPUT_DIR)/p_map.o			\
		$(OUTPUT_DIR)/p_maputl.o		\
		$(OUTPUT_DIR)/p_plats.o		\
		$(OUTPUT_DIR)/p_pspr.o			\
		$(OUTPUT_DIR)/p_setup.o		\
		$(OUTPUT_DIR)/p_sight.o		\
		$(OUTPUT_DIR)/p_spec.o			\
		$(OUTPUT_DIR)/p_switch.o		\
		$(OUTPUT_DIR)/p_mobj.o			\
		$(OUTPUT_DIR)/p_telept.o		\
		$(OUTPUT_DIR)/p_tick.o			\
		$(OUTPUT_DIR)/p_saveg.o		\
		$(OUTPUT_DIR)/p_user.o			\
		$(OUTPUT_DIR)/r_bsp.o			\
		$(OUTPUT_DIR)/r_data.o			\
		$(OUTPUT_DIR)/r_draw.o			\
		$(OUTPUT_DIR)/r_main.o			\
		$(OUTPUT_DIR)/r_plane.o		\
		$(OUTPUT_DIR)/r_segs.o			\
		$(OUTPUT_DIR)/r_sky.o			\
		$(OUTPUT_DIR)/r_things.o		\
		$(OUTPUT_DIR)/w_wad.o			\
		$(OUTPUT_DIR)/wi_stuff.o		\
		$(OUTPUT_DIR)/v_video.o		\
		$(OUTPUT_DIR)/st_lib.o			\
		$(OUTPUT_DIR)/st_stuff.o		\
		$(OUTPUT_DIR)/hu_stuff.o		\
		$(OUTPUT_DIR)/hu_lib.o			\
		$(OUTPUT_DIR)/s_sound.o		\
		$(OUTPUT_DIR)/z_zone.o			\
		$(OUTPUT_DIR)/info.o				\
		$(OUTPUT_DIR)/sounds.o

all: outputDirectory $(OUTPUT_DIR)/OSXdoom

clean:
	rm -f *.o *~ *.flc
	rm -f $(OUTPUT_DIR)/*
	rmdir $(OUTPUT_DIR)

.PHONY: outputDirectory

outputDirectory:
	mkdir -p $(OUTPUT_DIR)

$(OUTPUT_DIR)/OSXdoom:	$(OBJECTS) $(OUTPUT_DIR)/i_main.o
	$(CC) $(CFLAGS) $(LDFLAGS) $(OBJECTS) $(OUTPUT_DIR)/i_main.o \
	-o $(OUTPUT_DIR)/OSXdoom $(LIBS)

$(OUTPUT_DIR)/%.o:	%.c
	$(CC) $(CFLAGS) -c $< -o $@

#############################################################
#
#############################################################