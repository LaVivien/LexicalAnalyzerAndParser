# Lexical Analyzer and Parser

## Problem to Solve 

Consider the following grammar, which is the same as the one given on page 175 of the textbook, with the exception of the first rule. The first rule, <assign> is added for assignment statements. <assign> will be the starting symbol of your grammar. 
```
<assign> → id = <expr> 
<expr> → <term> {(+ | -) <term>} 
<term> → <factor> {(* | /) <factor>} 
<factor> → id | int_constant | ( <expr> )
```
The respective parser program modules for all the rules, except for the assignment statement, are given on pages 175-178 of the textbook. You will have to add a module for the assignment statement.

Convert the recursive-descent parser program given on pages 175-178 of the textbook to Java and modify it to parse assignment statements.

Your program must be well written and formatted.

## Lexical Analyzer

You may use your own lexical analyzer to read the actual statements to be parsed from a file called sourceStatements.txt. Your lexical analyzer must then generate the appropriate tokens for the parser.

If your lexical analyzer is not functioning well, in the Parse class, write a method, lex(), which inputs the already generated tokens from the statements.txt file described below and passes them to the parser. The method lex() must read and display the lines, which start with the phrase “Parsing the statement:”. In other words, the only elements which will be sent to the parser will be the tokens, not the source statements.

## Input

Test the parser using the supplied text file, which is called statements.txt. 

## output 

The output of your parser ought to be similar to the sample output below.
```
Parsing the statement: sumTotal = (sum + 47 ) / total
Next token is: IDENT
Enter <assign>
Next token is: ASSIGN_OP
Next token is: LEFT_PAREN
Enter <expr>
Enter <term>
Enter <factor>
Next token is: IDENT
Enter <expr>
Enter <term>
Enter <factor>
Next token is: ADD_OP
Exit <factor>
Exit <term>
Next token is: INT_LIT
Enter <term>
Enter <factor>
Next token is: RIGHT_PAREN
Exit <factor>
Exit <term>
Exit <expr>
Next token is: DIV_OP
Exit <factor>
Next token is: IDENT
Enter <factor>
Exit <factor>
Exit <term>
Exit <expr>
Exit <assign>
END_OF_FILE
```