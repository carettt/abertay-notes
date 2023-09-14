[2022-09-16], 22:39
Type: #lecture
Topics: [[C++]], [[Programming]]

## Variables and Data Types

Introduction to variables and data types.

---

### Primitives
- `char`
	- stores single characters
	- denoted by single quotations
	- `'a'`
- `int`
	- stores integers
	- signed long int by default
		- 4 bytes
	- can be set to unsigned and short
		- `unsigned short int nuts = 65534;`
		- short integers are 2 bytes
- `float`
	- stores decimals
	- stores 6 decimal places
- `double`
	- stores decimals
	- stores 10 decimal places
- `bool`
	- stores `true` or `false` values

> [!INFO]
> When you declare a variable, you are allocating space in the memory

---

### Strings
- Strings are *not* primitives
- Useful string functions
	- length
		- returns length of string
	- capacity
		- returns char capacity of string
	- append
		- ***mutates*** string and appends to it
	- compare
		- takes in a string (and other optionals)
		- returns 0 if strings are equal
		- returns >0 if the first character that does not match is greater (?) in the *compared string* or all the characters match but the *compared string* is shorter
		- returns <0 if the first character that does not match is lower (?) in the *compared string* or all the characters match but the *compared string* is longer
	- find
		- takes in start position
		- returns position if the string is found
	- insert
		- takes in start position and string
		- ***mutates*** string and inserts new string at position

---

### Input and output

```cpp
int main() {
	unsigned short int balls;

	cout << "How many balls do you have: ";
	cin >> balls;
	cout << end1;

	cout << balls << " is a lot of balls";
	cout << end1;
}
```

>[!ATTENTION]
>Use camelCase for variables in C++. Woo!


