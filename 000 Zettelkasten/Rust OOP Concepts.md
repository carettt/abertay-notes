2022-12-31, 11:50
Type: #zettel 
Tags: [[Rust]], [[OOP]], [[Programming]]

---

### Summary

Rust isn't completely OOP, inheritance is structured differently with `traits`, they allow shared functionality without copying more code than necessary.

### `struct`

A struct is similar to typing an object:

```rust
pub struct Collection {
	list: Vec<i32>,
	average: f64,
	total: i32,
	median: i32
}

// -- Implement Functions --

fn main() {
	let arr = Collection {
		list: vec![1, 2, 1],
		average: 1.3,
		total: 4,
		median: 1
	};
}
```

To add methods to our `struct` and make it similar to a `class`, we need to use the `impl` keyword:

```rust
impl Collection {
	pub fn checkTotal(&self) -> bool {
		let mut actualTotal = 0;
		for i in self.list {
			actualTotal += i;
		}
		if actualTotal == self.total {
			true
		} else {
			false
		}
	}
}
```

If a `struct` is being created from variables with the same name, i.e.:

```rust
let myCollection = Collection {
	list: list,
	average: average,
	total: total,
	median: median,
}
```

We can use a *shorthand declaration*:

```rust
let myCollection = Collection {
	list,
	average,
	total,
	median,
}
```

### `trait`

A `trait` is a [[Rust Data Types#Dynamically Sized Types (DSTs)]], this means it has to be referenced behind a pointer of some sort.

It can be defined with a set of function prototypes:

```rust
trait Draw {
	fn draw(&self);
}
```

We can implement the trait with the `impl` and `for` keywords:

```rust
pub struct Button {
	pub width: u32,
	pub height: u32,
	pub label: String,
}

impl Draw for Button {
	fn draw(&self) {
		// -- draw button --
	}
}
```

You can use this trait now with [[Rust Data Types#Generics]]:

```rust
pub struct Screet<T: Draw> {
	pub components: Vec<T>,
}

impl<T> Screen<T> where T: Draw {
	pub fn run(&self) {
		for component in self.components.iter() {
			component.draw();
		}
	}
}
```

This is a bit clunky and only allows for *homogenous* types, this means that Screen is allowed to be filled with a *single* type (i.e. all Button ***or*** TextField), rather than *heterogenous* types, (i.e. Button ***and*** TextField). We can use the `dyn` keyword to allow for the latter:

```rust
pub struct Screen {
	pub components: Vec<Box<dyn Draw>>,
}

impl Screen {
	pub fn run(&self) {
		for component in self.components.iter() {
			component.draw();
		}
	}
}
```

---

## References

[Rust Book - Chapter 17](https://doc.rust-lang.org/book/ch17-00-oop.html)
