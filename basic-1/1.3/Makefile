CC=gcc
CFLAGS=-I.
DEPS = hellomake.h

%.o: %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)


hellomake.o: hellomake.c hellomake.h
	gcc -c -o hellomake.o hellomake.c -I.


hellomake: hellomake.o hellofunc.o 
	gcc -o hellomake hellomake.o hellofunc.o -I.
