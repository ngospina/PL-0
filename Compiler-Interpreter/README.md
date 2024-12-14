# PL/0 Compiler-Interpreter system
**PL/0** compiler and **PL/0 machine** interpreter system [[1]](#1) written in **ISO Pascal**. The system is based on the program [[2]](#2) published in the book *Algorithms + Data Structures = Programs* by *Niklaus Wirth*.

|File   |Description                                  |
|-------|---------------------------------------------|
|pl0.pas|PL/0 Compiler Interpreter system (ISO Pascal)|

**Free Pascal compilation**
```
fpc -Miso pl0.pas
```

**Execution**
```
pl0 program-file listing-file
```

**PL/0 EBNF Grammar**
```
program    = block "." .
block      = [ "CONST" ident "=" number { "," ident "=" number } ";" ]
             [ "VAR" ident { "," ident } ";" ]
             { "PROCEDURE" ident ";" block ";" } statement .
statement  = [ ident ":=" expression | "CALL" ident |
             "BEGIN" statement { ";" statement } "END" |
             "IF" condition "THEN" statement |
             "WHILE" condition "DO" statement ] .
condition  = "ODD" expression |
             expression ( "=" | "#" | "<" | "<=" | ">" | ">=" ) expression .
expression = [ "+" | "-" ] term { ( "+" | "-" ) term } .
term       = factor { ( "*" | "/" ) factor } .
factor     = ident | number | "(" expression ")" .
``` 

<a id="1">[1]</a>
Original [**PL/0** Compiler-Interpreter system (ISO Pascal)](https://github.com/classic-tools/PL-0/tree/main/ISO-Pascal)\
<a id="2">[2]</a>
[**PL/0** Compiler-Interpreter system (CDC Pascal - 1976)](https://github.com/classic-tools/PL-0/tree/main/CDC-Pascal)
