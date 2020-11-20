################################################################################
#                                     MAKEFILE                                 #
################################################################################

# Binairy name
TARGET 		= exe

# Compiling options
CC 		    = g++
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
SOURCES        := $(wildcard $(SRCDIR)/*.cpp)
INCLUDES       := $(wildcard $(INCDIR)/*.h)
OBJECTS        := $(SOURCES:$(SRCDIR)/%.cpp=$(OBJDIR)/%.o)

# Rm option
RM 		= rm -f

############################### COMPILING RULES  ###############################

all : $(BIN)

$(BIN) : $(OBJECTS)
	@$(LINKER) $@ $(OBJECTS) $(LFLAGS)

$(OBJECTS) : $(OBJDIR)/%.o : $(SRCDIR)/%.cpp
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
