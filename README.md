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
| `/` | Division | We use `/` instead of `÷` because that symbol's not on keyboards|
| `**` | Exponentiation | We use `**` instead of `^` because `^` means something else in programming languages|
| `()` | Association | Expressions inside of `()` get evaluated earlier|

Back then, we didn't know how to use _variable lookup_ _expressions_ yet. We
had an intuitive grasp of how _operators_ worked with _constant expressions_
like `5 + 1`. Knowing what `5` and `1` and `+` mean meant that we could guess
that the expression would _evaluate_ to `6`.

But how does Ruby work with an expression like `x + 1`? It uses the "_variable
lookup expression_!"

![Box shake out](https://curriculum-content.s3.amazonaws.com/programming-univbasics/the-assignment-expression/Image_87D_VariableNamingMetaphors.png)

When Ruby sees a variable in an expression it swaps **in** the variable's value
_as if_ a _constant expression_ were there.

## Trace Resolution of Variables to Scalar Values to Return Value

```ruby
x = 1 # Assignment expression of constant value 1 to variable x
x + 2 #=> 3 ; Variable lookup "replaces" x with 1 and then evaluates 1 + 2 => 3
```

Keep in mind that swapping in a constant value, for Ruby, is the same as
swapping in a complex expression that must be evaluated to produce a value.

```ruby
x = 3 * (10 - 4)
x + 2 # Ruby "sees" (3 * (10 - 4)) + 2
(3 * (10 - 4)) + 2
(3 * 6) + 2
(18) + 2
18 + 2 #=> 20; Ruby does the necessary substitutions until it evaluates data and operators
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

And don't forget that losing negative things is positive!

```ruby
11 - -11 #=> 22
```

## Recognize `*` as the Symbol For Multiplication

The symbol for the multiplication is an asterisk, `*` so that we don't confuse it with the
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

That's surprising! Division is a little bit different in Ruby-land.

## Identify How Division in Ruby Differs from Normal Division

Now we just saw something a little bit strange, and it's related to "data
type," which we just learned about in the previous lesson.

In Ruby and most programming languages, numbers can be `Integer`s (whole
numbers), or `Float`s (decimal numbers). When you divide `Integers` by one
another, Ruby doesn't want to upset you by returning a non-`Integer`, it thinks
you're a "big picture" kinda thinker &mdash; "just stuff to the left of the
decimal, please."

So, `9 / 2` is `4` and the remainder (`½`) is helpfully left off.

By the same reasoning, if _one_ of the numbers in the expression were a
`Float`, Ruby would get the hint that we want a precise answer, and it would
respond correctly.

```ruby
9.0 / 2 #=> 4.5
```

Obviously, two `Float`s in a division tells Ruby you're very concerned about
details and will return a `Float`:

```ruby
9.0 / 2.0 #=> 4.5
```

Take those "surprising" results from the previous section, make one, the other,
or both `Float`s and verify that you're back to getting the precision you
expect.

## Conclusion

We now have the ability to perform most complex arithmetic calculations. We're
on our way to launching rockets to the Moon!
