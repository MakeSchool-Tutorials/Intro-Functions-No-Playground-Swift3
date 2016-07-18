---
title: "Custom Functions"
slug: custom-functions
---

Let's try creating our own, custom function. We just developed a procedure for drawing a square, wouldn't it be nice to have a `drawSquare()` function?

## Defining functions

We've already learned how to call functions, but how do we create our own?

```
func functionName() {
    // "function body"
    // function's code goes here
}
```

We use the keyword `func` to define a function (similar to how we use `var` for variables and `let` for constants). The function's name (`functionName` in our example) comes after the `func` keyword and it is followed immediately by parentheses. This is then followed by This is then followed by matched curly braces `{` and `}`. These are located near the enter key on your keyboard -- you'll need to hold the shift key to type them.

All your function's code should be put inside the curly braces. Any code inside the curly braces will be executed whenever the function is called.

## Your first function

> [challenge]
> Try defining your own `drawSquare` function below `// custom functions go below here` but above `// custom functions go above here`. Use the sample function above as a reference but make sure to change the name! You should be able to copy your square drawing code from before and paste it inside of the function body.

<!--  -->

> [action]
> Now that you have the function defined, empty out all the code below `// drawing code goes below here` but above `// drawing code goes above here`. Run the project to test it out!

## Did it work?

Did the visualization draw a square like you planned it to? Why not?

**Defining a function does not execute the code!**

You still must call the function to execute it's code. If you followed the steps closely, nothing will have happened to your drawing visualization because you only defined a new function, you never called it.

> [action]
> Go back up and add a new line of code to call `drawSquare` (below `// drawing code goes below here` but above `// drawing code goes above here`). Now run the project and you should see a square drawing on the screen!

## Naming functions

Keep in mind that function names must follow the same rules at variable names.

- must start with a letter of the alphabet
- may contain any alphanumeric character, plus some additional ones, like underscores
- may not contain spaces

## Indentation

You might have also noticed that we indented everything in the "function body". _It is common practice in programming to indent once (one press of the tab key if Xcode doesn't do it automatically) for every time you open a curly brace._ __Pay attention to our indentation and try to match it when you code. It's really important for readability that you follow this practice!__

# A "bigger" challenge

## Drawing a bigger square

> [challenge]
> Time to put those function skills to the test. In the last page you should have defined a `drawSquare` function. Define a `drawBigSquare` function after your `drawSquare` function. This new function should draw a square with sides _twice_ the length of your previous `drawSquare` function.

<!--  -->

> [info]
> Remember to call the `drawBigSquare` function instead of the `drawSquare` function once it's defined and make sure the visualization works as expected.
