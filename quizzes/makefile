cs:

OS       := $(shell uname)
VALGRIND := $(shell which valgrind)

ifeq ($(OS), Darwin)
	BOOST :=
else
	BOOST := -I/public/linux/include/boost-1_38
endif

.PRECIOUS: %.c++.app

%.c++.app: %.c++
	g++ -ansi -pedantic $(BOOST) -Wall $< -o $@

%.c++x: %.c++.app
	$(VALGRIND) $(patsubst %.c++x,%.c++.app,$@)

clean:
	rm -f *.c++.app
