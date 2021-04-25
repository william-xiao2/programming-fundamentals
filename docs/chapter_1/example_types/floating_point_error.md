# Floating Point Error

So, if we have both integers and floats, and every integer can be represented
by a float, why even bother having integers? Floats can do everything
integers can do, and more, right?

Well, not quite. To see this for yourself, try entering `0.1 + 0.2` into
the Python shell.

We'd expect to get back 0.3, as that is the mathematical answer to that expression.
However, Python actually gives us back:
```
>>> 0.1 + 0.2
0.30000000000000004
```
Huh? Where did all the trailing zeros and the 4 at the very end come from?

This hints at the exact reason why we need both ints and floats - *floats are inexact.*
Floats give a much higher level of precision on regular decimal numbers, but
because of the limitations of how computers store floats under the hood and
calculate these mathematical expressions, there may sometimes be a very small
margin of error.

Integers do not have this problem. As long as you stay within the integers,
doing math operations on integers will always give you the answer you expect.

In day-to-day operations, the floating point errors are generally are not
cumbersome enough to cause a large amount of worry. Even if you do a large
amount of float operations, the errors can propagate, but is still not a
huge worry. These kinds of concerns matter much more when absolute precision
in numbers is of utmost importance (scientific computing being an example).