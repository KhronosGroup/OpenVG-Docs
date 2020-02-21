#-------------------------------------------------------------------------------
# Export OPENVG_LOC as a environment variable if OpenVG is
# in a different location e.g.
# export OPENVG_LOC=/home/devuser/projects/openvg
#-------------------------------------------------------------------------------

#-------------------------------------------------------------------------------
# OpenVG Implementation Definitions
#-------------------------------------------------------------------------------
OPENVG_INC 	= include
OPENVG_LIB 	= lib
OPENVG_LIB_NAME = OpenVG

#-------------------------------------------------------------------------------
# CTS Definitions
#-------------------------------------------------------------------------------
ANSWER_CONFIG = -DANSWER_DEFAULT_DIR=\"../../../../data/answer\"
INFO_CONFIG   = -DINFO_DEFAULT_DIR=\"../../../../data/info\"
VGU_CONFIG    = -DTEST_OPTION_VGU=1

#-------------------------------------------------------------------------------
# Source Path Definitions
#-------------------------------------------------------------------------------
CTS_SRC    =../../source

#-------------------------------------------------------------------------------
# Compiler Environment Definitions
#-------------------------------------------------------------------------------
CC 	   =  gcc
INC        = -I$(OPENVG_INC) -I$(CTS_SRC)
LD_FLAGS   = -L$(OPENVG_LIB)  -L$(OPENVG_LOC)/lib -L/usr/X11R6/lib
LIBS       = -l$(OPENVG_LIB_NAME) -lEGL -lX11
CFLAGS     = $(INC) $(ANSWER_CONFIG) $(INFO_CONFIG) $(VGU_CONFIG)

#-------------------------------------------------------------------------------
# Source & Object Lists
#-------------------------------------------------------------------------------
TARGET     = bin/generator.exe

SRCS       = $(CTS_SRC)/*.c \
             $(CTS_SRC)/adopter/native/native_x.c \
	     $(CTS_SRC)/util/*.c \
	     $(CTS_SRC)/functions/*.c

#-------------------------------------------------------------------------------
# Module Specific Rules
#-------------------------------------------------------------------------------
all :	
	$(CC) -g $(CFLAGS) $(SRCS) -o $(TARGET) $(LD_FLAGS) $(LIBS)