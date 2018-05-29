# Video Outline

### Intro

*Present myself to begin with*

- UI design involves aligning/lining up control nodes precisely, matching margins and proportions
- On top of the anchor and layout system, Godot's 2d workspace comes with a grid, guides, and smart snapping tools to help you place and align your UI components faster
<!-- Show some UI alignment example in the intro / NB: you can reuse footage from the end of the video/recording to do so -->
- In this video you'll learn how to use
    - the grid and grid snapping options
	- Guides, virtual lines to help align sprites together
    - The smart snapping options

### Preparation
- To use the snapping options we first have to activate snapping
- Click the blue magnet in the toolbar or press S to toggle it on and off

### Grid snapping
By default any 2d or Control node will snap to the grid. Press G to make it visible.
- snapping will also work if the grid is hidden
- It allows us to move our nodes on a  grid-like environment
	- If you have already used tile maps (in or outside godot) it's pretty similar
- Although it may seem basic, most UI designers use grid snapping to place and move sprites around quickly and precisely
- Godot's default grid is 10px by 10px
	- To change this click the 3 dots next to the magnet icon -> Configure Snap
	- This menu allows us to configure snapping for both the grid and rotation steps
	- A lot of sprites you'll find online use powers of two for their sizes so it's common to use similar values for your grid. In general you'll want to set it based on your game's sprites' size
        - You should use your grid as a base unit to set the size and position of your your UI elements in fixed steps. It will save you time
		- For instance, the 4 bars at the top of our UI, the bottom ones are offset exactly by half the length of the top ones. This was easily done using the grid snap.
		- Each time we move the bar on the X axis, we are moving it 1 fourth of the bars' length

	- The offset setting will add an offset on the X and Y if needed.
		- The grid starts off at the origin of your game (X= 0; Y =0)
		- In case we don't want it to start there, we can add an offset to it
- The grid also works on 2D nodes, and it's usually a good idea to always keep it on when placing and moving nodes as it'll help us keep them aligned correctly

### Guides and Smart Snapping

On top of the grid, Godot 3 provides guides and Smart Snapping tools. Guides are infinite horizontal and vertical lines you can place anywhere and use as a visual reference or to snap nodes to
To see guides in the viewport go to View -> Show Guides. Press Y to toggle guides visible.
Make sure that you have rulers turned on as well as you'll drag guides from them.
	- go to View -> Show Ruler or press R

To create a new Guide, click and drag from the horizontal or the vertical ruler. Click and drag from the top left corner of the ruler to create both horizontal and vertical guides at the same time
Notice guides use your snapping options: they align with the grid or to the nodes' bounding boxes
To move a guide, click and drag from the ruler, starting on the purple line
To delete a guide, drag it back into the ruler

To snap to the guide, you'll need to turn on "Snap to Guide" on the Smart Snapping menu
This was used on our GUI scene.
	- Notice that the buttons at the bottom are offset on the Y position of the grid
	- I used a Guide to define to align the top edges of my UI components
- On the Map scene, I am using Snap to Other Nodes to keep the obstacles against one another
	- This was only possible because the Obstacle Scene has a sprite which is offset from its root
	- The reason behind using Snap to Other Nodes instead of using the grid is because the grid was too big for our SmallObstacles.
	- We could've also decreased the size of the grid instead of using this smart snap setting, which brings us to the point said at the beginning, the Grid is one ofr the most powerful and versitile tools that you have at your disposal
- Snap to parent will snap your node's origin to its parent's bounding rectangle
	- *Show example*

### Pixel Snap, Relative Snap and Rotation Snap

Let's look at a last few basic, yet essential snapping options

- Use pixel snap to force your nodes to snap to the pixel grid. This is important for pixel art games as placing them between pixels will lead to visual artifacts
	- *zoom in and show behavior*
- Relative snap is useful when we have a node that's offset from the main grid but we still want it to move in grid steps
	- *Offset the player and turn on Relative Snap*
	- As you can see, the player is still moving on a grid, but this time the grid is relative to this node's origin
- Lastly, rotation snap allows us to rotate nodes in fixed increments
	- *Rotate the player*

### Heads up

- The `Snap to node anchor` option only works with control nodes
	- As they are the only node type that have anchors
- As the grid is dense, when you use grid snapping it will generally take precedence over other snapping options
<!-- NB: this is due to the grid's size, if it's small there are many snapping candidates near your mouse cursor all the time. -->
