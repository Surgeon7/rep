CC = gcc -g -O0
KEK = makefile

task9: main.o func1.o func2.o func3.o
	$(CC) -o $@ $?

main.o: main.c
	$(CC) -c $<

func1.o: func1.c func1.h
	$(CC) -c $<

func2.o: func2.c func2.h
	$(CC) -c $<

func3.o: func3.c func3.h
	$(CC) -c $<

.PHONY : clean clean_all run install dis info help

clean:
	rm -rf *.o *~

clean_all:
	rm -rf task *.o manual

run: task
	./$<

install: task
	cp task ~/bin

dis:
	zip task.zip *.c *.h $(KEK)

info: *.h
	sed /#/d *.h > manual

help:
	@echo   make  - компиляция проекта
	@echo make run - запуск проекта
	@echo make install - установка скомилированного проекта
	@echo make dis - создание дистрибутива проекта
	@echo make info - создание документации
	@echo make clean - очситка без удаления исполняемого файла
	@echo make clean_all - полная очистка
	@echo make help - справка 
