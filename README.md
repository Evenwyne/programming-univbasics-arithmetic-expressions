# Arithmetic Expressions

## Learning Goals

* Trace Resolution of Variables to Scalar Values to Return Value
* Recognize `+` as the symbol for addition
* Demonstrate the addition operator
* Recognize `-` as the symbol for subtraction
* Demonstrate the subtraction operator
* Recognize `*` as the symbol for multiplication
* Demonstrate the multiplication operator
* Recognize `/` as the symbol for division
* Demonstrate the division operator
* Identify how division in Ruby differs from normal division

## Introduction

When we first introduced _expressions_, we presented a series of _operators_
and their corresponding _operations_ that were familiar from basic arithmetic:

|Operator|Operation|Note|
|--------|---------|----|
| `+` | Addition ||
| `-` | Subtraction ||
| `*` | Multiplication | We use `*` instead of `×` because it looks like `x`-the-letter|
| `/` | Division | We use `/` instead of `÷` because that's not on a keyboard|
| `**` | Exponentiation | We use `**` instead of `^` because that means something else in programming languages|
| `()` | Association | Expressions inside of `()` get evaluated earlier|

Back then, we didn't know how to use _variable lookup_ _expressions_ yet. We
had an intuitive grasp of how _operators_ worked with _constant expressions_
like `5 + 1`. But how does Ruby work with an expression like `x + 1`?

Amazingly, when Ruby sees a variable in an expression it swaps **in** the
variables value _as if_ a constant expression were there. To use the metaphors
we introduced already, it looks up that variable name's "definition..."

Lookup Fig 1B

...or it shakes the "content of the box labeled with the variable name"

Lookup Fig 2B

...and gets the value _back out_. Let's explore that!

## Trace Resolution of Variables to Scalar Values to Return Value

```ruby
x = 1 # Assignment expression of constant value 1 to variable x
x + 2 #=> 3 ; Variable lookup "replaces" x with 1 and then evaluates 1 + 2 => 3
```

Keep in mind that swapping in a constant value, for Ruby, is the same as
swapping in a complex expression that must be evaluated to produce a value.

```ruby
x = 3 * (10 - 4)
x + 2 # => 20; Ruby "sees" (3 * (10 - 4)) + 2; evaluates it and returns 20
```

## Recognize `+` as the Symbol for Addition

Addition's symbol should look familiar. The symbol that is used to perform this
operation is `+`.

## Demonstrate the Addition Operator

To get a feel for performing addition operations in Ruby, let's experiment. Open
up IRB by opening your terminal; type `irb` and hit enter and type the commands
below:

```ruby
10 + 1 #=> 11
```

```ruby
5 + -1 #=> 4
```

## Recognize `-` as the Symbol for Subtraction

Like addition, the symbol for subtraction, `-`, is also the same as in common
arithmetic.

## Demonstrate the Subtraction Operator

Let's experiment again. Open IRB and type these commands below:

```ruby
4 - 13 #=> -9
```

And don't forget that losing negative things is a positive!

```ruby
11 - -11 #=> 22
```

## Recognize `*` as the Symbol For Multiplication

The symbol for the multiplication is an asterisk, `*`, so that we don't confuse it with the
letter `x`.

## Demonstrate the Multiplication Operator

Use IRB and try typing the following the multiplication commands:

```ruby
10 * 10 #=> 100
```

```ruby
11 * -11 #=> -121
```

If everything was typed correctly, your results should be `100` and `-121`.
Nothing out of the ordinary, right?

## Recognize `/` as the Symbol For Division

The symbol for the division is a forward slash: `/`. There's no handy `÷`
character on most keyboards, so programmers adopted `/`.

***Division behaves differently in Ruby than you might expect***

Pay attention as we demonstrate it.

## Demonstrate the Division Operator

Open up IRB and try typing the following the division commands:

```ruby
8 / 3 #=> 2
```

```ruby
4 / 13  #=> 0
```

That's surprising! Clearly division is a little bit different in Ruby-land.

## Identify How Division in Ruby Differs from Normal Division

Now we just saw something a little bit strange, and it's related to "data
type," which we just learned about in the previous lesson.

In Ruby, and most programming languages, numbers can be `Integer`s (whole
numbers), or `Float`s (decimal numbers). When you divide `Integers` by one
another, Ruby doesn't want to upset you by returning a non-`Integer`, it thinks
you're a "big picture" kinda thinker &mdash; "just stuff to the left of the
decimal, please."

So, `9 / 2` is `4` and the remainder (`½`) is helpfully left off.

By the same reasoning as above, if _one_ of the numbers in the expression were
a `Float`, Ruby would get the hint that we want a precise answer, and it would
respond correctly.

```ruby
9.0 / 2 #=> 4.5
```

Obviously two `Float`s in a division will return a `Float`:

```ruby
9.0 / 2.0 #=> 4.5
```

Take those "surprising" results from the previous section, make one, the other,
or both `Float`s and verify that you're back to conversing with Ruby as you'd
expect, using IRB.

## Conclusion

Wow that was amazing! We took three lessons to learn three expressions
foundational expressions, but in this lesson we were able to build on them and
add 4 more expression. We can now even use IRB as a simple calculator. Not bad!
