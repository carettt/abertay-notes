2023-01-01, 20:18
Type: #zettel 
Tags: [[Programming]], [[Rust]], [[Debugging]]

---

### Summary

Rust supports automated testing in order to prove that existing correct behaviour does not change with new features.

### Format

There is a format to writing tests:

1. Set up any needed data or states
2. Run the test code
3. Assert (`assert_*` macros) results are expected

### Syntax

Tests are normally run in `lib.rs` under a `tests` module, they are defined as follows:

```rust
#[cfg(test)]
mod tests {
	use super::*; // Import library

	#[test]
	fn works() {
		assert_eq!(2, 2, "something is seriously wrong");
	}

	#[test]
	#[should_panic(expected = "does not equal")]
	fn doesnt_work() {
		assert_eq!(2, 3, "2 does not equal 3");
	}
	#[test]
	fn result_works() -> Result<(), String> {
		Ok(())
	}

	#[test]
	#[should_panic]
	fn result_doesnt_work() -> Result<(), String> {
		Err("does not work")
	}
}
```

### Organization Convention

There are three types of tests: unit tests, integration tests, and doc-tests.

#### Unit Tests

Unit tests are small tests that test a specific part of code (a single function or structure). The convention is to have a module at the end of the file of which code is being tested.

```rust
// src/lib.rs

// Library code

#[cfg(test)]
mod tests {
	#[test]
	#[should_panic]
	fn should_fail() {
		panic!("ahhhhhhhhhhhhhhhhhhhhhh");
	}
}
```

#### Integration Tests

Integration tests allow for broader, more complex tests that are similar to how end-users will use the library. They are written inside the `tests` folder and are only compiled with `cargo test` and not `cargo build`.

``` tests/integration_test.rs
use lib;

#[test]
fn setup_lib() {
	lib::setup();
}
```

#### Doc Tests



---

## References

