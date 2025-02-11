CC = gcc
CFLAGS = -Wall -Werror -Wextra -std=c11
LIBS = ../data_libs/data_io.c ../data_libs/data_stat.c main_executable_module.c ../data_module/data_process.c ../data_libs/sort.c ../yet_another_decision_module/decision.c
OBJECTS = $(LIBS:.c=.o)
QUEST_3 = ../../build/Quest_3
QUEST_5 = ../../build/Quest_5
STATIC = data_stat.a
AR = ar rcs

all: $(QUEST_3)

$(QUEST_3):$(OBJECTS)
	$(CC) $(CFLAGS) -o $@ $^ 

%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

build with static: $(STATIC) $(OBJECTS)
	$(CC) $(OBJECTS) $(STATIC) -o $(QUEST_5)

$(STATIC): ../data_libs/data_stat.o
	$(AR) $@ $<

clean:
	rm -rf $(OBJECTS) $(QUEST_3) $(QUEST_5) $(STATIC)

.PHONY: clean rebuild

rebuild: clean all