Dynamic Values provide a way to define the size and position of UI elements in a more flexible and adaptive manner. They allow you to create expressions that depend on the properties of other UI elements or the parent container, ensuring that your layout remains responsive and adaptive to changes in the available space or context.

### Basic Syntax

Dynamic Values are defined using expressions enclosed in double quotes (" "). These expressions can include arithmetic operations, as well as references to properties of other UI elements, such as their width or height.

Here's an example of a simple Dynamic Value expression:

```lua
"parent.w / 2"
```

This expression calculates half of the parent container's width.

### Using Dynamic Values for Size and Position

To use Dynamic Values for the size and position of UI elements in Basalt, simply pass the Dynamic Value expression as an argument to the relevant method, such as `setSize()` or `setPosition()`.

Here's an example of how to use Dynamic Values to set the size of a frame:

```lua
local mainFrame = basalt.createFrame()
local childFrame = mainFrame:addFrame():setSize("parent.w / 2", "parent.h / 2")
```

In this example, the child frame's size is set to half of the parent frame's width and height.

### Combining Dynamic Values with Static Values

You can also combine Dynamic Values with static values when defining the size and position of UI elements. For example, you can use a Dynamic Value for the width and a static value for the height.

Here's an example of how to do this:

```lua
local mainFrame = basalt.createFrame()
local childFrame = mainFrame:addFrame():setSize("parent.w / 2", 10)
```

In this example, the child frame's width is set to half of the parent frame's width, while its height is set to a static value of 100 pixels.

### Accessing Different Attributes

Dynamic Values can be used to access various attributes of a UI element, such as:

1. `x` The x-coordinate of the element
2. `y` The y-coordinate of the element
3. `w` The width of the element
4. `h` The height of the element

### Object Accessors

You can use different accessors to refer to objects when using Dynamic Values:

1. `parent` Access the parent object
2. `self` Access the current object
3. `ObjectID` Access a specific object using its ObjectID

This allows for a more dynamic and responsive layout, as you can adjust an element's attributes based on the properties of other elements. Here's an example of using Dynamic Values to set the position and size of a UI element:

```lua
local main = basalt.createFrame()
local childFrame = main:addFrame()

-- Set the size of the child frame to half the width and height of its parent frame
childFrame:setSize("parent.w / 2", "parent.h / 2")

-- Position the child frame at the center of its parent frame
childFrame:setPosition("parent.w / 2 - self.w / 2", "parent.h / 2 - self.h / 2")
```

In this example, the child frame's size and position are dynamically calculated based on the parent frame's dimensions, ensuring a responsive layout that adapts to changes in the parent frame's size.

Here's an example using ObjectIDs with Dynamic Values:

```lua
local main = basalt.createFrame()
local frameA = main:addFrame("frameA"):setSize(20, 20)
local frameB = main:addFrame("frameB"):setSize(10, 10)

-- Position frameB to the right of frameA
frameB:setPosition("frameA.x + frameA.w + 2", "frameA.y")
```

### Using Math Functions with Dynamic Values

In addition to basic arithmetic operations, you can also use functions from the Math Library within Dynamic Values expressions. This allows you to perform more complex calculations and transformations as needed.

For example, you can use the `math.floor()` function to round down the result of a division operation:

```lua
"math.floor(parent.w / 2)"
```

This expression calculates half of the parent container's width and rounds the result down to the nearest integer.

Here's an example of how to use a Math function within a Dynamic Value expression to set the size of a frame:

```lua
local mainFrame = basalt.createFrame()
local childFrame = mainFrame:addFrame():setSize("math.floor(parent.w / 3)", "math.ceil(parent.h / 4)")
```

In this example, the child frame's width is set to one-third of the parent frame's width, rounded down to the nearest integer, and its height is set to one-fourth of the parent frame's height, rounded up to the nearest integer.
