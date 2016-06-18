#
# Name: Makefile
#
# Copyright (C) 2014 wowotech
# Subject to the GNU Public License, version 2.

# Created By: wowo<www.wowotech.net>
# Created Date: 2014-01-23
#
# ChangeList:
# Created in 2014-01-23 by wowo;
#

CC = gcc
CFLAGS = -Wall -O3

INCFLAGS = -I$(shell pwd)/../libusb-1.0.20/out/include/libusb-1.0/
LDFLAGS = -L$(shell pwd)/../libusb-1.0.20/out/lib/ -lusb-1.0

OBJS = dfu.o dfu_board.o

OBJS += board_bubblegum.o

TARGETS = dfu

.PHONY:all
all:$(TARGETS)

$(TARGETS):$(OBJS)
	$(CC) -o $@ $^ $(LDFLAGS)

%.o:%.c
	$(CC) -o $@ -c $< $(CFLAGS) $(INCFLAGS)

%.d:%.c
	@set -e; rm -f $@; $(CC) -MM $< $(INCFLAGS) > $@.$$$$; \
	sed 's,\($*\)\.o[ :]*,\1.o $@ : ,g' < $@.$$$$ > $@; \
	rm -f $@.$$$$

-include $(OBJS:.o=.d)

.PHONY:clean
clean:
	rm -f $(TARGETS) *.exe *.o *.d *.d.*
