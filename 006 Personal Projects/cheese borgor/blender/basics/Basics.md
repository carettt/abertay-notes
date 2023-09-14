2023-03-31, 14:43
Type: #topic

Basics of Blender

---

### Common Shortcuts

- <kbd>A</kbd> to select everything
- <kbd>Alt-A</kbd> to deselect everything
- <kbd>Alt-LMB</kbd> select edge loop
- <kbd>L</kbd> to select joined
- <kbd>S</kbd> for scale
- <kbd>G</kbd> for grab / move
- <kbd>R</kbd> for rotate
- <kbd>Ctrl-R</kbd> for loop cut
- <kbd>U</kbd> for UV mapping menu
- <kbd>X</kbd>, <kbd>Y</kbd>, <kbd>Z</kbd> for snapping (most) commands to respective axis
- <kbd>MMB</kbd> for rotating view around object
- <kbd>Shift</kbd> + <kbd>MMB</kbd> for panning view
- <kbd>Num .</kbd> for centering to selection
- <kbd>Num 1</kbd> for front view
- <kbd>Num 7</kbd> for top view
- <kbd>Ctrl-Num1</kbd> for back view
- <kbd>Tab</kbd> to toggle edit mode
- <kbd>1</kbd>, <kbd>2</kbd>, <kbd>3</kbd> to select vertex, edge, and face select mode (respectively)

---

### UV Unwrapping

- Resetting rotation and scale
	- <kbd>Ctrl-A</kbd> to apply
	- Select rotation and scale
	- Fixes stretching on UV map
- Open UV editing workspace
	- Top tab <kbd>UV Editing</kbd>
- New texture
	-  Click on <kbd>New</kbd> on top of UV workspace
	- Give name
	- Disable Alpha
	- Select generated type to UV grid
	- Ok
- Create a new material
	- Exit edit mode
	- <kbd>Materials</kbd> tab and create a new material
	- Click on **yellow** circle that says Base Color
	- Select image texture
		- Select UV_Grid texture
	- Select material preview mode
		- Chequered sphere
	- NOTE texture is stretched and doesnt cover full barrel (which is why we need to UV unwrap)
- UV unwrap top of barrel
	- Enter edit mode
	- Select all faces
		- note you can see faces on UV grid
		- remove uv grid texture from uv window to see faces clearly
			- click <kbd>x</kbd> next to texture name
	- Deselect everything
	- Edge select
	- Select topmost edge loop
	- <kbd>RMB</kbd> -> <kbd>Mark Seam</kbd>
		- This will make a cut on the UV map
	- Select all faces
	- <kbd>U</kbd> to open UV mapping menu -> <kbd>Unwrap</kbd>
		- You can rotate and move the UV island for the top face of the barrel to map the texture onto the model
		- The UV island will not be perfectly round
			- Select all faces
			- Open UV mapping menu -> <kbd>Unwrap</kbd>
			- Open unwrapping menu -> <kbd>Method</kbd> -> <kbd>Conformal</kbd>
	- Repeat for bottommost edge loop
- UV Unwrapping barrel wall
	- Back view
	- <kbd>LMB</kbd> Middle-Top Edge
	- <kbd>Ctrl-LMB</kbd> Middle-Bottom Edge
	- <kbd>RMB</kbd> -> <kbd>Mark Seam</kbd>
	- Select all -> Open UV Mapping Menu -> Unwrap
	- Deselect everything in UV workspace
	- <kbd>Alt-LMB</kbd> select edge loop
	- <kbd>RMB</kbd> -> <kbd>Align X</kbd> or <kbd>Align Y</kbd> depending on edge loop orientation
		- Repeat for all edge loops in barrel wall
- UV Unwrapping cork
	- Deselect everything
	- <kbd>Ctrl-Alt-LMB</kbd> to select edge *ring*
	- <kbd>RMB</kbd> -> <kbd>Mark Seam</kbd>
	-  Select lid with <kbd>L</kbd>
	- UV mapping menu -> Unwrap
-  Scaling UV map evenly
	- Select all UV map
		- <kbd>UV</kbd> -> <kbd>Average Islands Scale</kbd>
	-  Scale barrel wall by Y or X to make sure squares are all the same size
	- Select all islands and pack inside UV map
		- <kbd>UV</kbd> -> <kbd>Pack Islands</kbd>
	- Scale and rotate all textures until satisfied
	- UV map moving down should mean texture going up
		- If not:
			- Select UV island, <kbd>R</kbd> + <kbd>180</kbd> 