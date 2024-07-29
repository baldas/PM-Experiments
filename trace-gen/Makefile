

# CC, LD and AR are builtin-variables of Make (?= is useless in this case)
# To override these defines, you must use "make CC=cc" or change it here
# Linker set by default to the CC definition
LD = $(CC)
# Supposing all compilers has -I -L
# TODO -I$(SRCDIR) only for library build
#CPPFLAGS += -I$(INCDIR) -I$(SRCDIR) $(CUFLAGS)

# Only on linux / TODO make source compatible with non-pthread OS
LDFLAGS += -lpthread


BINS = tracegen

UNAME := $(shell uname)

.PHONY:	all clean

all:	$(BINS)

tracegen.o:	tracegen.c
	$(CC) $(CPPFLAGS) $(CFLAGS) $(DEFINES) -c -o $@ $<

# FIXME in case of ABI $(TMLIB) must be replaced to abi/...
$(BINS):	%:	%.o
	$(LD) -o $@ $< $(LDFLAGS)

clean:
	rm -f $(BINS) *.o
