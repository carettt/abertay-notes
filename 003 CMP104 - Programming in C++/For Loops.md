[2022-09-25], 19:11
Type: #lecture
Topics: [[C++]], [[Loops]], [[Programming]]

## For Loops

An introduction into loops wth fixed/counting/for loops

---

### Code without For loops
```cpp
int num = 0;

cout << "Enter a number: ";
cin >> num;
cout << "The number is: " << (num * 10) << endl;

cout << "Enter a number: ";
cin >> num;
cout << "The number is: " << (num * 10) << endl;

cout << "Enter a number: ";
cin >> num;
cout << "The number is: " << (num * 10) << endl;

// ...
```

---

### Code with For loops

```cpp
int num = 0;
for (int i = 0; i < 3; i++) {
	cout << "Enter a number: ";
	cin >> num;
	cout << "The number is: " << (num * 10) << endl;
}
```

___

### Explanation
Normally statements in a program execute one after the other in the order in which theyre written. THis is callled sequential (procedural) execution

C++ also allows you to control the flow using either seletion, or iteration.
