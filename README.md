# MicroJava-Compiler
--------------------

Implemented compiler for MJ (MicroJava) a small segment of Java programming language which contains integers, booleans and characters, with the entire specification and syntax specified in the documentation.
The project was done for the Program Compilers 1 course.

The implementation contains 4 phases:
- Lexic analysis - with the use of JFlex and the src/spec/mjlexer.lex specification to generate the proper lexer to parse the input files into tokens
- Syntax analysis - using abstract tree generating tool called AST-CUP, which generates a syntax analyzer for the input file according to the given grammar in src/spec/mjparser.cup
- Semantic analysis - which does further analysis on the input source code, checking if the syntax matches the documentation, by extending VisitorAdaptor and implementing visit methods for each node type and constructs the symbol table of the program using symboltable-1-1 library.
- Code generation - which uses a provided Code class from the mj.runtime library. It generates code according to the documentation in binary, by extending VisitorAdaptor and implementing visit methods that generate code for nodes in the abstract syntax tree. 

How to run - extract projekat.zip and import the project in Java IDE of choice. Import all libraries as Internal JAR files, in project properties. Class Compiler is a runnable class with main method and the expected first argument is path to the source file and the second argument is the output file path and name.

Test folder contains different tests for the language in form of source MJ files which can be edited in any text editor and .obj output files which can be run using the Run class of mj-runtime-1.1 library. 
