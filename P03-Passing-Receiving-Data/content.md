---
title: "Smarter Functions"
slug: passing-receiving-data
---

## Function parameters

Have you been wondering why there are parentheses after function calls? It's not just so they look different from variables. It's because you can sometimes pass data to functions!

So far, we have been using the hardcoded `moveFifty()` and `rotateNinety()` functions. While this works, wouldn't it be nicer to be able to say `move(75)`? Try it out inside your `runDrawing` function!

> [challenge]
>
- Can you move `25` units? `250` units? What about negative values?
- Can you figure out how to rotate custom amounts? Can you rotate clockwise instead of counter-clockwise?
- Can you combine these to draw a triangle (3 sides)? A pentagon (5 sides)? How about a hexagon (6 sides)?

## Recap

We can call both `move(50)` and `rotate(90)` to get the same outcome as `moveFifty()` and `rotateNinety()`. You can put _any_ whole number in the parentheses and move custom amounts! The value we put in the parentheses is a _function parameter_.

# drawTriangle, drawPentagon, drawHexagon

## Pseudocoding

Let's beef up our polygon drawing skills.

> [action]
> Get out a pen and some paper. We'll be writing some pseudocode before we type out any Swift code.
>
> Go through the same exercise we did for squares but do it for triangles (3 sides), pentagons (5 sides), and hexagons (6 sides):
>
> ## Test it out!
>
> Draw the polygon with pen and paper. How would you use the `move` and `rotate` functions to draw that polygon? Write out each step. Read back each line of code to yourself and "perform" each function by hand. Did it work?
>
> ## Hint
>
> Here's a little hint for those of you who haven't thought about geometry in a while. The angle you rotate is called the polygon's exterior angle. The exterior angle is the angle formed from the extension of one side to the extension of another.
>
> You can calculate a polygon's exterior angle with the equation exteriorAngle = 360 / numberOfSides. You'll notice `360 / 4 = 90` which was correct for a square -- try it out on a few other polygons to confirm this should work!

## Implementation

**Did you actually do the above exercise? If not, go back to _Pseudocoding_ and do it. Don't cheat yourself!**

> [challenge]
> Once you have functioning pseudocode for each of the polygons, take the time to translate your planned procedures into Swift. Define the `drawTriangle`, `drawPentagon`, and `drawHexagon` functions below `// custom functions go below here` but above `// custom functions go above here`. Make sure to test them by calling them from `runDrawing`!

# Passing Data to Functions

## Defining a function

Previously, we've seen how to call functions with and without parameters but only how to define a function with no parameters. Let's review really quickly

**Calling a function without parameters:**

```
functionName()
```

**Calling a function with 1 parameter:**

```
functionName(parameterValue)
```

**Defining a function without parameters:**

```
func functionName() {
   // "function body"
   // function's code goes here
}
```

Where `func` is the keyword used to define a function, followed by the function name, an empty pair of parentheses, and a pair of curly braces (`{` `}`) surrounding the code contained in the function.

## Adding a parameter to your function definition

**The general form of a function with one parameter is:**

```
func functionName(parameterOneName: parameterOneType) {
   // "function body"
   // function's code goes here
   // value passed in becomes a constant with the name parameterOneName
}
```

If you compare this to the earlier functions we defined, you'll see the difference is the parameter name and type inside of the parentheses. It starts off with the same keyword `func`, followed by the function name, parentheses and curly braces. Remember, anything "inside" the curly braces gets indented once (one press of the tab key if Xcode doesn't do it for you automatically).

A lot like the variables we defined before, parameters must specify their data type and you cannot call a function with anything of a different type. Parameter names are similar to variable names -- they should be concise and descriptive. Another programmer should know what they are going to be used for just by looking at their name.

## Quick review of data types

Data types describe information used in programming. They are important when defining variables/constants, performing operations on values, and passing parameters into functions. The basic data types you should be familiar with so far are:

- `Int`: whole numbers, when divided they output integer division -- result is always rounded down!
- `Double`: numbers with a decimal place
- `String`: combination of letters, numbers, and other characters -- cannot be used for arithmetic even if the `String` contains only numbers! String types must be surrounded with double quotes (`"this is a string!"`)

## A more versatile drawSquare

> [challenge]
> Let's create a new `drawSquare` function that accepts a parameter for size. This will allow one function to create squares of multiple sizes! We've already started you out in the space below -- `drawSquare` takes one parameter named `sideLength` of type `Int` (a whole number). Copy this to where you have your other custom functions and fill out the function's body!
>
```
func drawSquare(sideLength: Int) {
>
}
```
>
> Remember, `sideLength` becomes a constant inside of the function's body. You can directly use constants and variables as parameters when you call other functions! Test out your new method with a function call of `drawSquare(150)`.
>
> Make sure to call the drawSquare function after you have defined it! It needs to be called with a function parameter like we did on the previous page.

## All working?

> [challenge]
> Once you have the resizable `drawSquare` function working, do the same for `drawTriangle`, `drawPentagon`, and `drawHexagon`.

# Repeating Code

## A quick intro to "loops"

Now that you've rewritten your polygon functions a few times, you may have started to see a general pattern for drawing polygons. Grab your pen and paper again, let's see if we can reduce the number of lines of code we are using.

This time, see if you can rewrite each of your draw functions (`drawTriangle`, `drawSquare`, `drawPentagon`, and `drawHexagon`) so that they only reference `move` and `rotate` once each. How can you do this? We're going to add a new tool to your pseudocode toolbox: repeat _x_ times.

If you were to write:

```
repeat 4 times
    move 10
```

we would expect it to move a total of 40 units (10 units at a time).

> [action]
> As usual, write it down then "run the code" yourself by following the directions as you hopefully draw out the polygon.

## Looking good?

Time to translate this pseudocode into Swift! In Swift, the following pseudocode:

```
repeat 4 times
    move 10
```

would become:

```
for _ in 1...4 {
    move(10)
}
```

We'll go further into the details of this _for-loop_ syntax in later exercises. Right now, all you need to know is that you can generalize it as this:

```
for _ in 1...numberOfTimes {
    // "for-loop body"
    // code repeated numberOfTimes goes here
}
```

Like function bodies, the for-loop's body is enclosed in curly braces. Also, like function bodies, we indent an extra time each time we open a curly brace!

## Go for it!

> [challenge]
> Now that you know how to implement "for-loops" (repeat a few lines of code), reimplement your `drawTriangle`, `drawSquare`, `drawPentagon`, and `drawHexagon` methods below. Make sure they are still resizeable and be sure to test them out!

# Passing Even More Data to Functions

## Even more parameters

So far we've seen functions with no parameters and functions with one parameter. Let's try defining a function with two parameters! Can you guess what it might be?

## Generalized polygon function

You might have noticed where we have been heading: a `drawPolygon` function with parameters of `numberOfSides: Int` and `sideLength: Int`. Your function should look like this:

```
func drawPolygon(numberOfSides: Int, sideLength: Int) {
    // "function body"
}
```

> [info]
> Notice how we comma-separate the parameters. You can define a function to take in as many parameters as you want -- you just need commas in-between each parameter!

## Give it a shot

> [challenge]
> Create a `drawPolygon` function using the template above. You want to use a for-loop like we did on the last page!

## Calling functions with more than one parameter

How do you think this function would be called? A reasonable guess is that `drawPolygon(3, 100)` would create a triangle with sides of length `100` but no, that won't work!

The correct (and only way) you can call the function above is with the format `drawPolygon(3, sideLength: 100)`.

## What???

Some of you are now wondering why `drawPolygon(3, sideLength: 100)` works and `drawPolygon(numberOfSides: 3, sideLength: 100)` does not. By default, Swift requires a parameter label for each parameter after the first. If you do not explicitly specify a parameter label, it assumes you want to use the parameter name as the label too. This means the generalized format of calling a function with multiple parameters is:

```
functionName(parameterOneValue, parameterTwoName: parameterTwoValue)
```

> [challenge]
> Test your `drawPolygon` function and make sure it works!

# Returning data

## Return values

There's one last thing functions can do: return data! Great code is readable code and returning values from functions will help you get things organized.

Let's take a look at how to define a function with a return value.

> [info]
> A full circle is 360 degrees or 2π radians. A half circle is 180 degrees or π radians. A quarter circle is 90 degrees or π/2 radians.
>
> `M_PI` is a Swift constant that represents π as a `Double`

```
func radiansToDegrees(radians: Double) -> Double {
  return radians * 180 / M_PI
}

let halfPiRadiansInDegrees = radiansToDegrees(M_PI / 2)
let piRadiansInDegrees = radiansToDegrees(M_PI)
let twoPiRadiansInDegrees = radiansToDegrees(2 * M_PI)
```

## Defining functions with return values

**The general form of a function with a return value is:**

```
func functionName() -> ReturnType {
    // "function body"
    return valueToReturn
}
```

You can add as many parameters as you would like but the important part is:

1. `-> ReturnType` where `ReturnType` is the data type of the value you are returning (`Int`, `Double`, `String`, etc)
2. `return valueToReturn` where `return` is a required keyword telling Swift to immediately exit the function and give the value back to it's caller. `valueToReturn` must be the same type as you specified earlier in `ReturnType`

> [info]
> The function must return a value of `ReturnType` with the `return` keyword no matter what!

## Degrees to radians

It's time for you to define your own function with a return value!

> [challenge]
> Write a `degreesToRadians` function. It should accept one parameter called `degrees` of type `Double` and return a `Double`.
>
> **Hint**
>
> You can convert from degrees to radians by inverting the math in the above function. Divide by `180` and multiply by `M_PI` (π).
>
> Half of π is roughly 1.57, π is roughly 3.14, 2π is roughly 6.28. Make sure your function returns the correct values!

# One more drawPolygon rewrite

> [challenge]
> Write a `calculateRotationForPolygon` function that takes one parameter called `sides` of type `Int` and returns a `Double`. Update your `drawPolygon` function to use `calculateRotationForPolygon`.

> [info]
> Remember that you will need to _cast_ `sides` from an `Int` to a `Double`. Swift is very specific about types! You can _cast_ or convert it with `Double(sides)`.
