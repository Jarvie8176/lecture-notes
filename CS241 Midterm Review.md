CS241 Midterm Review

## MIPS Programming


> `swap.asm`
> 
> linkable using cs241.linkasm
> 
> input: $1, $2 containing valid mem addr
> result: swaps content of locations

```
.export swap

swap:
sw $31, -4($30)		; not necessary
sw $3, -8($30)
sw $4, -12($30)

lis $31
.word 12
sub $30, $30, $31

add $3, $1, $0
lw $3, 0($1)
lw $4, 0($2)
sw $3, 0($2)
sw $4, 0($1)

lis $31
.word 12
add $30, $30, $31
lw $31, -4($30)
lw $3, -8($30)
lw $4, -12($30)

jr $31					; important
```

> program that uses input from mips.array, and calls "swap" to swap contents of the first and last item

```
.import swap

main:
sw $31, -4($30)
sw $3, -8($30)
sw $4, -12($30)
sw $5, -16($30)

lis $31
.word 16
sub $30, $30, $31

lis $4
.word 4
mult $4, $2
mfhi $4
sub $4, $1, $4


add $1, $0, 0($3)		; not necessary
add $2, $0, 0($4)

lis $5
.word swap
jalr $5

lis 531
.word 16
add $30, $30, $31


lw $31, -4($30)
lw $3, -8($30)
lw $4, -12($30)
lw $5, -16($30)

jr $31
```

## Assembler concepts

### symbol table

* loader behaviour

	* ignore merl header / footers

	* start addr at ```[starting addr] - [0xc]```

## DFA / NFA

* see `Note 1`

* see `Note 2`

* see `Note 3`

* see `Note 4`

