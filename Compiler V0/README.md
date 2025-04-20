# COMPILER V0

This is a compiler for a VERY BASIC language I'm making.

The code is in Python as that's the language I'm used to.
No, the code is not good, it just does what it needs to do.

In some cases, I've used an inefficient method for the sake of practice.
For example, I know that I could just use python.re for the lexer, but that defeats the fun of the project.

## Types

This is a simple language which only contains booleans and integers.
There are no lists/arrays (Again, simple language).

## Syntax

```
//This is a comment
#This is also a comment

#Declaration
bool varA = true #Defines a Boolean variable called varA and assigns true
int varB = 12 #Defines an integer variables called varB and assings 12
int varC = false //THIS IS NOT VALID

#Assignment
varA = false #Assigns false to varA
varB = false //THIS IS NOT VALID

#Boolean operations
bool varC = false
bool varD = false
bool varE = false
varC = true or false
varC = varC and not varA
varD = varA xor varC
varE = varA and varB == 12

#Integer operations
int varF = 0
int varG = 0
varF = varB + 35
varG = varF - 7
varF = varB * varG
varB = varB ^ 2 #Square varB 
varG = varF / 2 #Divide varF by 2 (rounds down)

#Selection
if varA == true then varB = 1 else varB = 0
//There are no functions in this language

#Iteration
for 15 varB = varB + 1

#Debug
out varB  #Prints the value in varB - MUST BE A VARIABLE
```

# Lexer Regex

```
Keyword = true | false | bool | int | + | - | * | / | ^ | or | not | and | xor | = | == | if | then | else | for | out
Identifier = [a-zA-Z][a-zA-Z_\\-0-9]*
Whitespace = \\  | \t | \n
Number = [0-9]+
Comment = ( // | # ).*

R = Keyword | Identifier | Whitespace | Number | Comment
```

Note: Comment > Whitespace > Keyword > Number > Identifier
