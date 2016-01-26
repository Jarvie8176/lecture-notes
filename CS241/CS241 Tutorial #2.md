CS241 Tutorial #2

# MIPS Programming

* Instructions
* Stack
* 32 Registers
	
	| Registers | Usage  |
	|-----------|--------|
	| $31       | return |
	| $30       | stack  |
	| $29       | float  |
	| $0        | zero   |
	

## Example - Fibonacci numbers

* input
	* $1 = n

* output
	* $3 = nth fib number

```
fib:	sw $1, -4($30)		; save variables on stack
		sw $2, -8($30)
		sw $4, -12($30)
		sw $5, -16($30)

init:	lis $2				; constant
		.word 1
		add $3, $0, $0
		1add $4, $2, $0
		
		
begin:	beq $1, $0, end
		sub $1, $1, $2		; sub by 1
		add $5, $4, $0		; $5 is temp of $4
		add $4, $3, $4		; compute next item
		add $3, $5, $0		; $3
		beq $0, $0, begin
		
end:	lis $2
		.word 16
		add $30, $30, $2
		
		lw $5, -16($30)
		lw $4, -12($30)
		lw $2, -8($30)
		lw $1, -4($30)

		jr $31
		
		
main:	lis $5
		.word fib
		lis $6
		.word print
		
		add $7, $1, $0		; $7 = n
		add $8, $0, $0		; $8 is counter
		
		sw $31, -4($30)		; save the PC to current addr
		lis $2
		.word 4
		
		sub $30, $30, $2
		
		jalr $5

```