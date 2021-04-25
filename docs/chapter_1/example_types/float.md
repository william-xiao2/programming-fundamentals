## Type `float`

The type `float` represents numbers with decimal points. The term `float`
is short for "floating-point number", a term used in computer science to
represent numbers with decimal points.

This decimal point is the main distinguisher between ints and floats.
For example, `2` is an int, but `2.0` is a float. The fact that we have decimal
points allows us to represent values we could not before, such as `2.5`.

## Operators
Operations-wise, floats are similar to ints. They support the same
addition, subtraction, multiplication, etc. operations, all with the same
principle that operations on floats should yield floats. However, division
on floats is slightly different. Now, dividing two floats is done with `/`
instead of `//` (so, one forward slash instead of two forward slashes).

Seeing this in action in the Python shell:
```
>>> 1.0 / 2.0
0.5
```
We now get the 0.5 that we could not get before when dividing ints.