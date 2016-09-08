## Context-free grammar

* prove that the given stuff is context-free grammar but not regular

	* by contradiction

* ambiguity

	```
	S -> AA
	A -> epsilon
	A -> x
	```
	
	* see `Note 1`

* left-canomical and right canomical derivation

	* example

		* string "aaabbc"

			* left

				```
				S => aABc
				A => aA
				A => aA
				A => epsilon
				B => bb
				```
				
			* right
			
				```
				S => aABc
				B => bb
				A => aA
				A => aA
				A => epsilon
				```
				
## Top-Down parsing

* example

	* given grammar below, parse string `dfeaccb`

	```
	0. S' -> |- S -|
	1. S -> aYb
	2. S -> XS
	3. Y -> ccZY
	4. Y -> epsilon
	5. X -> dZe
	6. Z -> f
	7. Z -> epsilon
	```

	* see `Note 2`

	* predictor table - see `Note 3`

	* stack - see `Note 4`

## Button Up Parsing

* example

	* give same grammar below, parse string `dfeaccb`

	```
	0. S' -> |- X -|
	1. X -> XbAb
	2. X -> XaBa
	3. x -> epsilon
	4. A -> Aa
	5. A -> epsilon
	6. B -> Bb
	7. B -> epsilonss1pcc
	```

	* see `Note 5`

## error checking

* compiler workflow

	* program text

	* scanner / tokenizer: **lexical error**

	* parser: **syntax error**

	* codegen / semantic analyser: **semantic error**

	* assembler

## Code Generation

* terms

	* `$3` - return value from code

* example

	* adding bitshifting operators `<<` and `>>` to WLP4, what in language spec should be added

		* token
		
			* `<<`
			* `>>`

		* production rule

			* `bitExpr -> bitExpr << expr`
			* `bitExpr -> bitExpr >> expr`
			* `bitExpr -> expr`
			* all existing rules with expr on RHS should be changed to bitExpr
				* includes ` ... -> bitExpr`

		* type rule

			 * similar to rules in spec

	* pesudo code

		
		* `bitExpr -> bitExpr << expr`:
		
			```
			code(bitExpr)
			push ($3)
			code(expr)
			pop($5)
			lis $2
			.word 2
			
			loopX:
			beq $3, $0, endX
			mult $5, $2
			mflo $5
			sub $3, $3, $11
			beq $0, $0, loopX
			
			endX:
			add $3, $5, $0
			```
			
* example

	* adding `for` loops to WLP4, assume excatly 1 assignment in init portion, 1 test and 1 assignment in the increment portion.

		* token

			* `for`

		* production rule

			* `statemnet -> for ( assignment; test; assignment) { statements }`
			* `assignment -> lvalue = expr;`

		* type rule / semantic rule

			* `well-type(assignment), well-type(test), ... |- well-typed(for)`

		* code
		
			```
			initX:
			code(statement1)
			
			loopX:
			code(test)

			beq $3, $0, endX
			code(statements)
			code(assignment2)
			beq $0, $0, loopX
			
			endX:
			
			```

## optimization and memory management

* optimization

	* constant folding

		* a = 1 + 2 + 3; => a = 6;

	* dead code elimination

	* register allocation

* memory management

	* internal fragmentation
	
		* getting extra chunk of data

	* external fragmentation