[[2022-12-21]], 21:23
Type: #zettel 
Tags: [[Rust]], [[Programming]]

---

Variables in rust are immutable by default, they can be mutable by adding the `mut` keyword:

```rust
let x = 5;
let mut y = 5;
x += 1; // not allowed
y += 1; // allowed
```

Rust allows you to 'shadow' variables (mostly used for type conversion):

```rust
let x: String = "5";
let x: u32 = x.parse().unwrap();
```

You can print variables easily using `{}`:

```rust
let name = "aksdjfasd";
println!("my name is {name}");
```

Rust also has constants, they are similar to immutable variables with four differences:
- Constants are always immutable (i.e. the keyword `mut` is not allowed when declaring consts)
- The type of the value *must* be annotated, (i.e. `const NUMBER: u32 = 34256`)
- Constants can be declared in any scope (including the global scope), wheras variables cannot
- Constants can only be set to a *constant expression*, this means that the value has to be known at compile-time, not runtime, i.e.:
```rust
use std::io;

const HOURS_TO_SECONDS: u32 = 60 * 60; // valid

fn main() {
	let mut input;
	io::stdin()
		.read_line(&mut input)
		.unwrap();
	
	const INPUT_IN_SECONDS: u32 = input.parse().unwrap() * HOURS_TO_SECONDS; // invalid
}
```

---

## References