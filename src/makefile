# 编译加了libpmem库的源文件时加上-l pmem参数进行编译
# 在这个makefile中添加ycsb测试的相关编译命令，运行ycsb

DIR_INC = ./include
DIR_SRC = ./src

CC = gcc
CFLAGS = -O -Wall -m64 -std=gnu89
LIBS = -lm
 
$(DIR_TES)/ycsb: ycsb.cpp pm_ehash.o data_page.o
	$(CC) $(CFLAGS) ycsb.cpp pm_ehash.o data_page.o -o ycsb
	  
$(DIR_SRC)/pm_ehash.o：$(DIR_SRC)/pm_ehash.cpp $(DIR_INC)/pm_ehash.h
	$(CC) $(CFLAGS) -c $(DIR_SRC)/pm_ehash.cpp
	  
$(DIR_SRC)/data_page.o: $(DIR_SRC)/data_page.cpp $(DIR_INC)/data_page.h 
	$(CC) $(CFLAGS) -c $(DIR_SRC)/data_page.cpp
 
 
.PHONY: clean
clean：
	rm $(DIR_SRC)/*.o $(DIR_SRC)/ycsb 
