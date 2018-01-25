# Makefile template for shared library

CC = gcc # C compiler
CFLAGS = -fPIC -Wall -Wextra -O2 -g # C flags
LDFLAGS = -shared  # linking flags


SRCDIR = src
INCDIR = include
OBJDIR = obj
BINDIR = bin
LIBDIR = lib

CFLAGS += -I $(INCDIR)/

SOURCES  := $(wildcard $(SRCDIR)/*.c)
INCLUDES := $(wildcard $(INCDIR)/*.h)
OBJECTS  := $(SOURCES:$(SRCDIR)/%.c=$(OBJDIR)/%.o)
RM = rm -f  # rm command
MV = mv     # mv command
TARGET_LIB = libtarget.so # target lib

#SRCS = main.c src1.c src2.c # source files
#OBJS = $(SRCS:.c=.o)

.PHONY: all
all: ${TARGET_LIB}

$(TARGET_LIB): $(OBJECTS)
	@echo $(SOURCES)
	$(CC) ${LDFLAGS} -o $@ $^

$(OBJECTS): $(OBJDIR)/%.o : $(SRCDIR)/%.c 
	@echo $(INCLUDES)
	@$(CC) $(CFLAGS) -c $< -o $@
	@echo "Compiled "$<" successfully!"

$(SOURCES:.c=.d):%.d:%.c
	@echo "sources"
	$(CC) $(CFLAGS) -MM $< >$@

include $(SOURCES:.c=.d)

.PHONY: clean
clean:
	-${RM} ${TARGET_LIB} ${OBJECTS} $(SOURCES:.c=.d) ${LIBDIR}/${TARGET_LIB}
.PHONY: install
install:
	-${MV} ${TARGET_LIB} ${LIBDIR}/${TARGET_LIB}

