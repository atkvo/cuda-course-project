NAME=signdetector
CC=g++
SRC=signdetect.cpp

CFLAGS=
all:
	$(CC) `pkg-config --cflags --libs opencv` $(SRC) -o $(NAME)

clean:
	rm $(NAME)
