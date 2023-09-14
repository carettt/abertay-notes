2022-12-22, 17:19
Type: #zettel 
Tags: [[Rust]], [[Programming]]

---

#### Integers

| Length  | Signed | Unsigned |
| ------- | ------ | -------- |
| 8-bit   | i8     | u8       |
| 16-bit  | i16    | u16      |
| 32-bit  | i32    | u32      |
| 64-bit  | i64    | u64      |
| 128-bit | i128   | u128     |
| arch    | isize  | usize         |

Integers types are defined by either being signed or unsigned, `i` or `u` respectively, and giving their size in bits (as shown above).

Integer literals can be defined in different ways, `_`  is used as a visual separator (`1000` is the same as `1_000`). They can also be defined in different bases:

| Base   | Example     |
| ------ | ----------- |
| 10     | 45_453      |
| 16     | 0xf3        |
| 8      | 0o77        |
| 2      | 0b1011_1000 |
| 2 (u8) | b'A'            |

Integers will overflow if their value exceeds the space allocated, during debug mode, the program will panic and crash, when compiling in release mode, Rust will perform *two's complement wrapping* and wrap back around to 0.

---

#### Floats

Rust has two floating-point types, `f32`, and `f64`, `f64` is the default.

---

### Dynamically Sized Types (DSTs)

Rust needs to know the size of variables *before* compile-time, i.e.:

```rust
let s: str = "test string";
```

won't work, this is because a `str` type can be variable size... to fix this, we need to put `str` behind a pointer, the pointer will store the location of the type ***and*** the length of the type.

Thus, all DSTs should be referenced through a pointer (either `&` or `Box<T>`).

### Generics

Generics allows for less repetition of code, you can define generics by using `<>` and naming the generic type (convention is `T`, `U`, `V`, ...).

Generics are defined after the name:

```rust
struct Point<T> {
	x: T,
	y: T,
}
```

This would dictate that `x` and `y` are of same types, to make them different *or* same:

```rust
struct Point<T, U> {
	x: T,
	y: U,
}
```

In methods, `impl` only implements one type at a time:

```rust
impl Point<f32> {
	fn distance_from_origin(&self) {
		(&self.x.powi(2) + &self.y.powi(2)).sqrt()
	}
}
```

However, they can be implemented for all generic types:

```rust
impl<T> Point<T> {
	fn x(&self) {
		self.x
	}
}
```

---

## References

[Rust Book - Advanced Types](https://doc.rust-lang.org/book/ch19-04-advanced-types.html#dynamically-sized-types-and-the-sized-trait)
[Rust Book - Generic Data Types](https://doc.rust-lang.org/book/ch10-01-syntax.html)