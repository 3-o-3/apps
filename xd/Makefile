
#   Unix Makefile for xd

VERSION = 1.4

#   C compiler
CC = gcc

#   For production
CFLAGS = -O -Wall

#   For debugging
#CFLAGS = -g -Wall

xd:	xd.o
	$(CC) $(CFLAGS) xd.o -o xd

clean:
	rm -f xd *.bak *.cat core *.out *.o *.shar *.gz *.tar *.zip *.opt *.ncb *.plg

RELEASE = Makefile xd.1 xd.c index.html log.txt images

dist:
	rm -f *.tar *.tar.gz
	tar cfvz xd-$(VERSION).tar.gz $(RELEASE)

manpage:
	nroff -man xd.1 | more

printman:
	ptroff -man xd.1

catman:
	nroff -man xd.1 | col -b >xd.cat

#   The following tests should produce no error messages from XD or CMP

check:	testb testad testao testdd testdo

testb:	xd
	xd xd xd1.bak
	xd -l xd1.bak xd2.bak
	cmp xd2.bak xd
	xd -c xd xd3.bak
	xd -l xd3.bak xd4.bak
	cmp xd4.bak xd
	xd -l -s xd3.bak xd4.bak
	cmp xd4.bak xd
	sed 's/........//' xd3.bak >xd5.bak
	xd -l -s xd5.bak xd6.bak
	cmp xd6.bak xd
	echo Hello there >xd10.bak
	xd xd10.bak >xd7.bak
	sed '1d' xd3.bak >>xd7.bak
	xd -l -s xd7.bak xd8.bak
	cp xd10.bak xd9.bak
	tail --bytes=+17 xd >>xd9.bak
	cmp xd8.bak xd9.bak
	cat xd | xd -dDeFile >xd10.c
	echo "#include <unistd.h>\nint main() {write(1,DeFile,sizeof DeFile); return 0;}" >>xd10.c
	$(CC) xd10.c -o xd10.bak
	chmod 755 xd10.bak
	./xd10.bak >xd11.bak
	cmp xd11.bak xd
	rm xd*.bak xd10.c

testad: xd
	xd -ad xd xd1.bak
	xd -ad -l xd1.bak xd2.bak
	cmp xd2.bak xd
	xd -ad -c xd xd3.bak
	xd -ad -l xd3.bak xd4.bak
	cmp xd4.bak xd
	xd -ad -l -s xd3.bak xd4.bak
	cmp xd4.bak xd
	sed 's/........//' xd3.bak >xd5.bak
	xd -ad -l -s xd5.bak xd6.bak
	cmp xd6.bak xd
	echo Hello there >xd10.bak
	xd -ad xd10.bak >xd7.bak
	sed '1d' xd3.bak >>xd7.bak
	xd -ad -l -s xd7.bak xd8.bak
	cp xd10.bak xd9.bak
	tail --bytes=+17 xd >>xd9.bak
	cmp xd8.bak xd9.bak
	rm xd*.bak

testao: xd
	xd -ao xd xd1.bak
	xd -ao -l xd1.bak xd2.bak
	cmp xd2.bak xd
	xd -ao -c xd xd3.bak
	xd -ao -l xd3.bak xd4.bak
	cmp xd4.bak xd
	xd -ao -l -s xd3.bak xd4.bak
	cmp xd4.bak xd
	sed 's/........//' xd3.bak >xd5.bak
	xd -ao -l -s xd5.bak xd6.bak
	cmp xd6.bak xd
	echo Hello there >xd10.bak
	xd -ao xd10.bak >xd7.bak
	sed '1d' xd3.bak >>xd7.bak
	xd -ao -l -s xd7.bak xd8.bak
	cp xd10.bak xd9.bak
	tail --bytes=+17 xd >>xd9.bak
	cmp xd8.bak xd9.bak
	rm xd*.bak

testdd: xd
	xd -nd -ad xd xd1.bak
	xd -nd -ad -l xd1.bak xd2.bak
	cmp xd2.bak xd
	xd -nd -ad -c xd xd3.bak
	xd -nd -ad -l xd3.bak xd4.bak
	cmp xd4.bak xd
	xd -nd -ad -l -s xd3.bak xd4.bak
	cmp xd4.bak xd
	sed 's/........//' xd3.bak >xd5.bak
	xd -nd -ad -l -s xd5.bak xd6.bak
	cmp xd6.bak xd
	echo Hello there >xd10.bak
	xd -nd -ad xd10.bak >xd7.bak
	sed '1d' xd3.bak >>xd7.bak
	xd -nd -ad -l -s xd7.bak xd8.bak
	cp xd10.bak xd9.bak
	tail --bytes=+17 xd >>xd9.bak
	cmp xd8.bak xd9.bak
	rm xd*.bak

testdo: xd
	xd -no -ah xd xd1.bak
	xd -no -ah -l xd1.bak xd2.bak
	cmp xd2.bak xd
	xd -no -ah -c xd xd3.bak
	xd -no -ah -l xd3.bak xd4.bak
	cmp xd4.bak xd
	xd -no -ah -l -s xd3.bak xd4.bak
	cmp xd4.bak xd
	sed 's/........//' xd3.bak >xd5.bak
	xd -no -ah -l -s xd5.bak xd6.bak
	cmp xd6.bak xd
	echo Hello there >xd10.bak
	xd -no -ah xd10.bak >xd7.bak
	sed '1d' xd3.bak >>xd7.bak
	xd -no -ah -l -s xd7.bak xd8.bak
	cp xd10.bak xd9.bak
	tail --bytes=+17 xd >>xd9.bak
	cmp xd8.bak xd9.bak
	rm xd*.bak
