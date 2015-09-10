# compiler
Translation of Programing Languages

Klien Grammar

Here is the grammar for Klein. In this grammar, e, the lowercase Greek letter epsilon, stands for the empty string. It indicates that nothing is a legal alternative.

            <PROGRAM> ::= <DEFINITIONS>

        <DEFINITIONS> ::= <DEF>
                        | <DEF> <DEFINITIONS>

                <DEF> ::= <IDENTIFIER> ( <FORMALS> ) : <TYPE> <BODY>

            <FORMALS> ::= e
                        | <NONEMPTYFORMALS>

    <NONEMPTYFORMALS> ::= <FORMAL>
                        | <FORMAL> , <NONEMPTYFORMALS>

             <FORMAL> ::= <IDENTIFIER> : <TYPE>

               <BODY> ::= <PRINT> <BODY>
                        | <EXPR>

               <TYPE> ::= integer
                        | boolean

               <EXPR> ::= <EXPR> < <SIMPLE-EXPR>
                        | <EXPR> = <SIMPLE-EXPR>
                        | <SIMPLE-EXPR>

        <SIMPLE-EXPR> ::= <SIMPLE-EXPR> or <TERM>
                        | <SIMPLE-EXPR> + <TERM>
                        | <SIMPLE-EXPR> - <TERM>
                        | <TERM>

               <TERM> ::= <TERM> and <FACTOR>
                        | <TERM> * <FACTOR>
                        | <TERM> / <FACTOR>
                        | <FACTOR>

             <FACTOR> ::= if <EXPR> then <EXPR> else <EXPR> endif
                        | not <FACTOR>
                        | <IDENTIFIER> ( <ACTUALS> )
                        | <IDENTIFIER>
                        | <LITERAL>
                        | - <FACTOR>

            <ACTUALS> ::= e
                        | <NONEMPTYACTUALS>

    <NONEMPTYACTUALS> ::= <EXPR>
                        | <EXPR> , <NONEMPTYACTUALS>

            <LITERAL> ::= <NUMBER>
                        | <BOOLEAN>

              <PRINT> ::= print ( <EXPR> )

Note: The whitespace in the grammar is intended to aid readability. It is not significant

