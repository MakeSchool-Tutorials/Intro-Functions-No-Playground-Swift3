---
title: "Create Something Cool"
slug: create-something-cool
---

> [challenge]
> Use everything you learned to draw something awesome! See below for a few more functions you can use to bring your art to life!
>
> You should do this in `runDrawing()` and any create functions that will help you!

# Drop and lift the pen

## Drop the pen
```
penDown()
```

## Lift the pen
```
penUp()
```

> [info]
> The pen starts out down.

# Moving the pen

## Move by a number of steps
```
move(steps: Int)
```

## Move directly to coordinates
```
moveTo(x x: Int, y: Int)
```

> [info]
> This is called with labels for both parameters! For example...
>
```
moveTo(x x: 10, y: 40)
```

## Rotate heading by an angle
```
rotate(degrees: Int)
```

# Change the pen

## Set color of pen
```
setColor(red red: Double, green: Double, blue: Double)
```

> [info]
> This is called with labels for all 3 parameters! Each value should be between 0 and 1. For example...
>
```
setColor(red: 0.0, green: 0.0, blue: 0.0)
```
>
would change the pen to be black.
>
```
setColor(red: 1.0, green: 0.0, blue: 0.0)
```
>
would change the pen to be red.

## Set thickness of pen
```
setThickness(thickness: Double)
```

## Make the pen move faster
```
setDelay(delay: Double)
```
