# Video Outline

### Intro

*Present myself to begin with*

- UI Creation envolves a lot of lining control nodes correctly and mantaining proportions
- Godot provides tools for us to use when we are dealing with theses kinds of tasks (lining things up, keeping proportions)
- In this video, we'll take a look on...
	- Grid snapping
	- Smart Snapping
	- Guides
### Preparation
- In order to use any kind of snapping, we first have to activate it
- To do so, we click on the blue magnet

### Grid snapping
- It's the most basic and most powerful tool we have
- It allows us to move our nodes on a  grid-like environment
	- If you have already used tile maps (in or outside godot) it's pretty similar
- To show the grid we press G or go to View -> Show Grid
	- The snapping will also work if the grid is hidden
- Godot's default grid is a 10px by 10px
	- We can change this by going on the 3 dots besides the magnet -> Configure Snap
	- This menu allows us to configure the grid snap, as well as the rotation snap
	- It's usually a good idea to keep this as a multiple of 8, as most sprites that you see on games are also a multiple of 8 (16, 32, 64, 128, etc..)
	- This way you always move your nodes on a given proportion when in relation to other nodes
		- For instance, the 4 bars at the top of our UI, the bottom ones are offset exactly by half the length of the top ones. This was easily done using the grid snap.
		- Each time we move the bar on the X axis, we are moving it 1 fourth of its actual length
	- The offset setting will add an offset on the X and Y if needed.
		- The grid starts off at the origin of your game (X= 0; Y =0)
		- In case we don't want it to start there, we can add an offset to it
- The grid also works on 2D nodes, and it's usually a good idea to always keep it on when placing and moving nodes as it'll help us keep things aligned correctly

### Guides and Smart Snapping
- When the grid isn't enough, you can use guides and Smart Snapping to help you create your UI or game world
- To show the grid, press Y or go to View -> Show Guides and make sure that you have your Ruler turned on.
	- You'll know that it's turned on if you see these numbers on the top and left sides of your 2D view. If it's not, press R or go to View -> Show Ruler
- You can create a Guide by clicking and dragging from the ruler, either from top, left or top-left corner
- Once it's created, you can only move it by clicking and dragging it from your ruler
- The guide will respect snap configurations
	- Grid, and other smart snaps
- You can remove a guide by dragging it all the way to the top or the the left
- To snap to the guide, you'll need to turn on "Snap to Guide" on the Smart Snapping menu
- This was used on our GUI scene. 
	- You can notice that the buttons at the bottom are offseted on the Y position of the grid
	- We used the Guide to define a line where all the bottom controls should stay below and snapped them to it
- Keep in mind that the snap is always at the origin of your node
- On our Map scene, we are using Snap to Other Nodes to keep the obstacles together
	- This was only possible because the Obstacle Scene has a sprite which is offset from its root
	- The reason behind using Snap to Other Nodes instead of using the grid is because the grid was too big for our SmallObstacles.
	- We could've also decreased the size of the grid instead of using this smart snap setting, which brings us to the point said at the beginning, the Grid is one ofr the most powerful and versitile tools that you have at your disposal
- Snap to parent will snap your node's origin to it's parents Rect
	- *Show an example of this while I speak*

### Pixel Snap, Relative Snap and Rotation Snap
- Pixel snap will keep the nodes position always at a whole number
	- *zoom in and show behavior*
	- Can be useful when you have a really low res game
- Relative snap is useful when we have a node that's offset from the main grid but we also want to move it on a grid-like manner
	- *Offset the player and turn on Relative Snap*
	- As you can see, the player is still moving on a grid, but this time the grid starts at this node's origin
- Lastely, the rotation snap allows us to rotate nodes on a pre configured step
	- *Rotate the player to give an example*

### Heads up
- Snap to node anchor only works with control nodes
	- They are the ones which have anchors to begin with
- Grid snapping will *override* other snapping settings

