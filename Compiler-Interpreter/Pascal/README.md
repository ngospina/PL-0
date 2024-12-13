# PL/0 Compiler-Interpreter system
**PL/0** compiler and **PL/0 machine** interpreter system. The system is based on the program written in **Revised CDC Pascal** [[1]](#1).

|File   |Description                                          |
|-------|-----------------------------------------------------|
|pl0.pas|PL/0 Compiler Interpreter system (Revised CDC Pascal)|

**PL/0 EBNF Grammar**
```
program    = block "." .
block      = [ "CONST" ident "=" number { "," ident "=" number } ";" ]
             [ "VAR" ident { "," ident } ";" ]
             { "PROCEDURE" ident ";" block ";" } statement .
statement  = [ ident ":=" expression | "CALL" ident |
             "?" ident | "!" expression |
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
[**PL/0** Compiler-Interpreter system (Revised CDC Pascal - 1976)](https://github.com/classic-tools/PL-0/blob/main/PL0-1976/Revised-CDC-Pascal/pl0.pas)
