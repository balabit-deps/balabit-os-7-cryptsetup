TARGET=keyslot_test
CFLAGS=-O0 -g -Wall -D_GNU_SOURCE -I ../../lib/
LDLIBS=-ljson-c -luuid -lgcrypt -ldevmapper -lpthread -lssh
CC=gcc

TARGET2=keyslot_test_remote_pass
TARGET4=keyslot_add_by_key

SOURCES=keyslot_test.c
OBJECTS=$(SOURCES:.c=.o)
SOURCES2=keyslot_test_remote_pass.c
OBJECTS2=$(SOURCES2:.c=.o)
SOURCES4=keyslot_add_by_key.c
OBJECTS4=$(SOURCES4:.c=.o)

all: $(TARGET) $(TARGET2) $(TARGET4)

$(TARGET): $(OBJECTS) ../../.libs/libcryptsetup.a
	$(CC) -o $@ $^ $(LDLIBS)

$(TARGET2): $(OBJECTS2) ../../.libs/libcryptsetup.a
	$(CC) -o $@ $^ $(LDLIBS)

$(TARGET4): $(OBJECTS4) ../../.libs/libcryptsetup.a
	$(CC) -o $@ $^ $(LDLIBS)

clean:
	rm -f *.o *~ core $(TARGET) $(TARGET2) $(TARGET4)

.PHONY: clean
