2022-12-24, 21:16
Type: #zettel 
Tags: [[Graphics]], [[Programming]]

---

### Summary

OpenGL is an API to interact with a GPU and display on a screen.

### `sdl2` crate

To initialize OpenGL we first need to initialize SDL:

```rust
use sdl2;

fn main() {
	let sdl = sdl2::init().unwrap();
}
```

Then the video subsystem needs to be initialized :

```rust
let video = sdl.video().unwrap();
```

The video subsystem allows us to create a new window:

```rust
let window = video
	.window("Title", 900, 700)
	.resizeable()
	.build()
	.unwrap()
```

The window will now open and close immediately, we need to add a loop, and initialize the event pump, to avoid the window unresponsive message.

```rust
let mut event_pump = sdl.event_pump().expect("error initializing event pump");
loop {
	for _event in event_pump.poll_iter() {
		// 
	}
}
```

---

## References

[OpenGL](https://www.opengl.org/)