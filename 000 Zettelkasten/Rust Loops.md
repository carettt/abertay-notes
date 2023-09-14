2022-12-23, 16:51
Type: #zettel
Tags: [[Rust]], [[Programming]]

---

### Summary

Rust loops work the same as loops in other languages, however, they have some important discrepancies.

### `while let` loops

`while let` loops allow for while loops with pattern matching, they are equivalent to a loop with a `match` expression inside:

```rust
let mut x = vec![1, 2, 3];

loop {
	match x.pop() {
		Some(y) => println!("y: {}", y),
		_ => break,
	}
}
```

with a `while let` loop:

```rust
let mut x = vec![1, 2, 3];

while let Some(y) = x.pop() {
	println!("y = {}", y);
}
```

### Labelling loops

Rust allows you to label loops, this allows you to break from outermost loops rather than always the innermost loop.

```rust
'first: loop {
	loop {
		break 'first;
	}
}
println!("Out of both loops");
```

---

## References

[Rust Book](https://doc.rust-lang.org/reference/expressions/loop-expr.html)