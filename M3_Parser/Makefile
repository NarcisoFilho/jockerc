#
# UFRGS - Compiladores B - Marcelo Johann - 2009/2 - Etapa 1
#
# Makefile for single compiler call
# All source files must be included from code embedded in scanner.l
# In our case, you probably need #include "hash.c" at the beginning
# and #include "main.c" in the last part of the scanner.l
#

etapa3: SymbolTable.o y.tab.o lex.yy.o main.o AST.o   
	gcc -o etapa3 main.o lex.yy.o y.tab.o SymbolTable.o AST.o
main.o: main.c
	gcc -c main.c
lex.yy.o: lex.yy.c
	gcc -c lex.yy.c
lex.yy.c: scanner.l
	lex --header-file=lex.yy.h scanner.l
y.tab.o: y.tab.c
	gcc -c y.tab.c
y.tab.c: parser.y
	yacc -d parser.y
SymbolTable.o: SymbolTable.c
	gcc -c SymbolTable.c
AST.o: AST.c
	gcc -c AST.c

clean:
	rm etapa3 y.tab.c y.tab.h lex.yy.c lex.yy.h *.o