################################################################################
#                                   MAKEFILE                                   #
################################################################################

# Binairy name
TARGET 		= exe

# Compiling options
CC 		    = gcc
CFLAGS 		= -W -Wall

# Link options
LINKER 		= $(CC) -o
LFLAGS 		= -Wall

# Directories
BINDIR 		= bin
OBJDIR 		= obj
INCDIR 		= inc
SRCDIR 		= src

# Variables
BIN             = $(BINDIR)/$(TARGET)
SOURCES        := $(wildcard $(SRCDIR)/*.c)
INCLUDES       := $(wildcard $(INCDIR)/*.h)
OBJECTS        := $(SOURCES:$(SRCDIR)/%.c=$(OBJDIR)/%.o)

# Rm option
RM 		= rm -f

############################### COMPILING RULES  ###############################

all : $(BIN)

$(BIN) : $(OBJECTS)
	@$(LINKER) $@ $(OBJECTS) $(LFLAGS)

$(OBJECTS) : $(OBJDIR)/%.o : $(SRCDIR)/%.c
	@$(CC) -c $< -o $@  $(CFLAGS)

################################### CLEANER ####################################
.PHONY: clean
clean :
	@$(RM) $(OBJECTS)
	@$(RM) $(SRCDIR)/*~
	@$(RM) $(INCDIR)/*~
	@$(RM) *~

fclean : clean
	@$(RM) $(BINDIR)/$(TARGET)

################################################################################
