# Typecasting
**Typecasting** is the process of changing a value from one type to another.
For example, what if we had a boolean and we wanted to turn it into an int?
Or if we had a float and wanted to turn it into an int? We can do that!

The general form of this type casting is:
```
type(value)
```
where `type` is the name of the type (e.g. int, float, bool) you want to convert
into and `value` is the value you want to cast.

For example:

```
>>> int(True)
1
```
converts the boolean True to the integer 1, and

```
>>> float(5)
5.0
```
converts the integer 5 to the float 5.0, and

```
>>> bool(0)
False
```
converts the integer 0 to the boolean False.

## Automatic Typecasting
If you play around with Python, you'll see that sometimes, Python will do
operations meant for one type, even though you passed in a different type.
As an example, `/` is float division, and is meant to be applied to two floats.
However, if you try
```
>>> 1 / 2
0.5
```
Python doesn't crash and complain that you gave it a wrong type, but instead
it seemingly does float division here even though you gave it ints. What happened?

Well, Python knew that `/` only applied to float types, and that you gave
it ints. However, Python also knew that any integer could always be turned
into a float that represented the same value without any loss of information.
For example, any integer can be turned into an equivalent float by putting a
decimal point and a 0 after it, e.g. `2` and `2.0`. Since Python knew it could
do so without losing any information, it automatically did the conversion
for us under the hood and implicitly evaluated the above expression as `1.0 / 2.0`.

## Widening vs. Narrowing Casts
The above example of Python automatically converting 1 to 1.0 is an example of a
**widening cast**. In general, a widening cast converts a value into a different "wider"
type that can represent / hold more data. For example, casting a bool to an int
is a widening cast, and casting an int to a float is a widening cast.
Python will complete these casts automatically under the hood if doing so
is necessary for proper evaluation of the expression, since there are no
concerns to be had with losing information.

A **narrowing cast**, as the name implies, converts a value to have a different,
narrower type that can hold less information. For example, casting a float to
an int is a narrowing cast because ints cannot represent as much information
as floats. Python will never do this automatically for you, since doing so
can cause information to be lost. As an example, casting 2.0, 2.3, and 2.7
to ints using `int(2.0)`, `int(2.3)`, `int(2.7)` all yield 2. Information was
lost here (the numbers after the decimal point).

## String Type Conversion

You can *sometimes* convert between types when strings are involved. For example,
you can turn a boolean into a string:
```
>>> str(True)
'True'
```

and you can sometimes turn a string into a number, such as:
```
>>> int('2')
2
>>> float('3.14159')
3.14159
```

However, this conversion is not guaranteed to always succeed, whereas typecasts
between booleans, ints, and strings are. For example,

```
>>> int('abc')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: 'abc'
```

Attempting to turn the string `abc` into an integer caused Python to crash, as
one might expect. What is the numeric equivalent of that text? There is no
well defined answer.