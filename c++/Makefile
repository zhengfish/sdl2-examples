CXX?=g++
CXXFLAGS?=$(shell pkg-config sdl2 --libs --cflags)

.PHONY: all msg clean fullclean

all: msg main

msg:
	@echo --- C++ ---

main: main.cpp
	${CXX} -O3 main.cpp ${CXXFLAGS} -o main

small: main.cpp
	${CXX} -Os main.cpp ${CXXFLAGS} -o main
	strip main
	sstrip main

debug: main.cpp
	${CXX} -O0 -g main.cpp ${CXXFLAGS} -o main

run: msg main
	time ./main

clean:
	rm -f main

fullclean: clean
