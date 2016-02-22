###################
# Project Setting #
###################

# The C program name
BIN_NAME = MyProgram

# C Compiler
CC = clang

# Preprocessor Flags
CPP_FLAGS =  -I$(SRC_PATH)

# Compiler Flags
CC_FLAGS = -std=c99 -Wall -Wextra -g

# Linker flags
LD_FLAGS =

# Path to the source directory
SRC_PATH = ./src

# Path to the build directory
BIN_PATH = ./build


#######################################
# Setting for auto building C Program #
#######################################

# Dont use make built-in rules
.SUFFIXES:


# Define recursive wildcard
rwildcard=$(foreach d,$(wildcard $1*),$(call rwildcard,$d/,$2) $(filter $(subst *,%,$2),$d))


# Define list of file
TARGET  = $(BIN_PATH)/$(BIN_NAME)
SOURCES = $(call rwildcard, $(SRC_PATH), *.c)
OBJECTS = $(SOURCES:$(SRC_PATH)/%.c=$(BIN_PATH)/%.o)
DEPENDS = $(SOURCES:$(SRC_PATH)/%.c=$(BIN_PATH)/%.d)


# User friendly output unless verbose
COMPILE = @echo "[Compile] $@" && $(CC)
LINK    = @echo "[Link] $@" && $(CC) 
ifeq ($(VERBOSE),true)
		COMPILE = $(CC)
		LINK    = $(CC) 
endif


# Main target
.PHONY: all
all: $(TARGET)


# Remove all build files
.PHONY: clean
clean:
	$(RM) $(TARGET) $(OBJECTS) $(DEPENDS)


# Target build
$(TARGET): $(OBJECTS)
	$(LINK) $(OBJECTS) $(LD_FLAGS) -o $@ 


# Object build
$(BIN_PATH)/%.o: $(SRC_PATH)/%.c
	$(COMPILE) $(CC_FLAGS) $(CPP_FLAGS) -MP -MMD -c $< -o $@


# Add SOURCES file dependency if any
-include $(DEPENDS)




