CC=gcc
C_FLAGS=-std=gnu99 -Werror -fsanitize=address,undefined -g
#C_FLAGS=-Wall -Werror -pedantic -g
L_FLAGS=-lm -lrt -fsanitize=address,undefined
TARGETS=host guest
OBJECTS=host.o guest.o

.PHONY: all clean

all: host guest

guest: guest.o
	${CC} -o guest guest.o ${L_FLAGS}

guest.o: guest.c
	${CC} -o guest.o -c guest.c ${C_FLAGS}

host: host.o
	${CC} -o host host.o ${L_FLAGS}

host.o: host.c
	${CC} -o host.o -c host.c ${C_FLAGS}

clean:
	-rm -rf ${TARGETS} ${OBJECTS}
