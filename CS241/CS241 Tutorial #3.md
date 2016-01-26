CS241 Tutorial #3

# Symbol Table

## Construct a Symbol Table

```
begin:	
label:			beq $0, $0, after
				jr $4

after:		
				sw $31, 16($0)
				lis $4
			
abc0: abc1:	.word after

loadstore:
				lw $20, 4($0)
				sw $20, 28($0)
				
end:
```

* value of label: # of non-null lines that precedes a label multiplied by 4

	* non-null liens: lines that are ```instructions``` or ```.word```

--

NOTE: assuming program starts at 0

| labels    | value |
|-----------|-------|
| begin     | 0     |
| label     | 0     |
| after     | 8     |
| abc0      | 16    |
| abc1      | 16    |
| loadstore | 20    |
| end       | 28    |


# Identify Errors

* ```label: label: .word label```
	* **label: label:**

* ```.word ; 0```
	* no value for .word

* ```.word aaaaa```
	* **aaaaa**

* ```.word 1 2 3```
	* invalid # of arguments

* ```.word 2147483648 randomshit:```
	* ```randomshit:``` - can't have label after instruction

* ```.word ,```
	* ```,``` - invalid argument type

# Biwise Operators

* ```3 & 5 = 1```

```
0001
0101
----
0001	
```

* ```3 | 5 = 7```

```
0011
0101
----
0111
```

* ```3 << 2 = -4```

```
0011
 <<2
----
1100
```

* ```3 >> 2 = 0```

```
0011
 >>2
----
0000
```

* ```-3 << 2```

```

```

* ```-3 << 2 = 4```

```
1101
 <<2
----
0100
```

* ```-3 >> 2 = 1```

```
1101
 >>2
----
1111
```

* ```13 << 2 = ```


* ```13 >> 2 = ```



