[2022-10-02], 11:50
Type: #quick
Topics: 

## Binary Data Representation

Understanding how a computer represents information.

---
### Von Neumann Architechture
[IMAGE]
- start by looking at the main memory (how to store information)
- memory
	- the pigeon-hole model
	- series of numbered boxes
	- each one can hold a number
		- binary number
	- [IMAGE]

---

### Binary
- Electricity
	- two states
	- binary digits are bits
	- 8 bits = 1 byte
	- 16 or 32 bits = 1 word 
		- dependent on the computer system
- Number systems
	- decimal
		- base 10
	- binary
		- base 2
	- maximum number per cell is `base - 1`
	- cells are `previous * base`
	- MSB `111001` LSB
- naming the bits in a byte
	- write down the bits from left to right with the most significant bit on the left
	- rightmost bit is always called b0. the remaining bits are named b1, b2, b3

---

### Converting Decimal to Binary
- write down column headings
- write down number you want to convert
- convert

---

### Converting Binary to Decimal
- write down column headings
- *fill in* number you want to convert
- multiply rows
- add up

---

### Word Size
- Largest number that can be represented in n bit binary is
	- $2^n-1$
-  Maximum number of different values that can be represented in n bit binary is
	- $2^n$

---

### Address size vs address space
- For example
	- a computer with a 3 bit wide address bus
		- can have 8 addresses

---

### Binary Arithmetic
- Addition
	- When adding, there is a third row that is being added
	- There is also a carry-in bit, and a carry-out bit (the carry out bit is used to throw an overflow error)
- Subtraction
	- Adding a negative number using the same addition circuit
	- Negative Numbers
		- Sign-and-Magnitude
			- Take the leftmost bit to represent the sign
				- if `0` its positive, if `1` its negative
			- The problem is that there are two representations of 0
			- sign and magnitude is used in floating point representations
		- One's Complement
			- MSB is $-(MSB-1)$
			- To work out the One's complement representation of a -ve number
				- Find the +ve version
				- Flip the bits
		- Two's Complement
			- To work out the Two's Complement representation of a -ve number
				- FInd the One's Complement
				- Add 1
			- $-X=(2^n)-X$
			- The range of X is
				- $-2^{(n-1)}<X<(2^{(n-1)})-1$
			- All positive numbers have an MSB of zero
			- The value -1 looks like $2^n-1$ which is **all ones**, always
			- MSB is negative

---

### Hexadecimal
- Base 16
- Shorthand
	- 32 bit binary number
- 16 hex digits
	- 0-F
- Prefix with `0x` or postfix with `h`
- Two hex digits = 1 byte
- Convert hex to binary
	- Break into groups of 4 bits
	- use table to convert
- Each group of four bits can be known as a nybble

---

### ASCII
- American Standard Code for Information Interchange (ASCII)
- Uses one byte to represent one character
- there are 128 standard characters in the ASCII coding scheme
- THe unicode is used incomputers to represent extended characters
- Unicode supports alphabets of other languages and special characters
- [ASCII STANDARD CHART]

---

### Instructions
- Representations of program instructions
- Also stored as binary numbers
- The way they are interpreted, is based entirely on the program