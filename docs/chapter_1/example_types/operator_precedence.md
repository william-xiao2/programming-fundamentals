In middle school algebra, you learned about the order of operations when
evaluating mathematical expressions. You may recall PEMDAS, referring to
Parentheses, Exponents, Multiplication, Division, Addition and Subtraction,
which denoted the order in which simplifying operations were to occur.

Python follows these same rules when evaluating expressions. For example,
`1 + 2 * 3` gets evaluated as `1 + (2 * 3)` instead of `(1 + 2) * 3`.
However, Python has extra operators for comparison as well - how do those
play along with the math operators?

The simple answer is that math operations take precedence over comparison
operations (equals, greater than, less than, etc.) and comparison operations
take greater precedence over boolean operations (and, or, not).

More formally, in order, precedence is as follows:

1. Exponentiation
2. Unary operations (e.g. negation)
3. Multiply, Divide, Remainder
4. Add, Subtract
5. Comparison (`<`, `>`, `<=`, `>=`)
6. Equality (`==`, `!=`)
7. `not`
8. `and`
9. `or`


So, the expression
```
>>> 1 + 2 * 3 > 9 or not False
```

would internally be parsed as
```
>>> (((1 + (2 * 3)) > 9) or (not False))
True
```

