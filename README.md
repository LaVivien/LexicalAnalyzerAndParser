# Lexical Analyzer and Parser

## Problem to Solve 

Given the following grammar.
```
<assign> → id = <expr> 
<expr> → <term> {(+ | -) <term>} 
<term> → <factor> {(* | /) <factor>} 
<factor> → id | int_constant | ( <expr> )
```
Implement the recursive-descent parser program in Java.


## Lexical Analyzer

You may implement lexical analyzer to read the actual statements to be parsed from a file. Your lexical analyzer must then generate the appropriate tokens for the parser.

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