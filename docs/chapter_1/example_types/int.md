# Type `int`

The first type we will discuss is type `int` (this is how Python refers to it).
`int` is short for "integer" - the same definition of integer from math.
That is, the whole numbers and their negatives.

Some examples:
..., -3, -2, -1, 0, 1, 2, 3, ...

When entering an int expression into Python, you should only enter the digits
in the number. It is common in math to separate large numbers with commas
every three digits from the end - Python will misunderstand what you mean
if you enter commas, and produce a different value from what you might
initially expect (we will cover what the comma implies later on in this reference).

So, for example, if you wanted to enter the number one million, you would enter
`1000000` and not `1,000,000`.

{% hint style="info" %}
If you're dealing with large integers and you really want to separate out
the groups of three digits to improve readability, you can add underscores
where the commas would normally go, and Python will still interpret the number
normally as if you hadn't included the underscores. So, you could type
`1000000` and `1_000_000` and Python treats them as the same number.
{% endhint %}

What can we do with ints? Operations on ints include the standard math operations
that you learned in grade school. These include:

- `+` (Addition)
- `-` (Subtraction / negation)
- `*` (Multiplication)
- `//` (Division)
- `%` (Remainder)
- `**` (Exponent)

{% hint style="warning" %}
Notice how the exponent operator is `**`, not `^`. `^` is another operator
that does not compute exponentiation. If you use `^` with the intention of
computing an exponent, you will most likely get the wrong value.
{% endhint %}

## A note on operations
There is a general rule that operations on `int` values should yield `int`s in
return. This seems straightforward for operations like addition, where typing
`1 + 2` at the shell gives us `3`, another int. However, what happens when
we do division? If we try to divide 1 by 2,

```
>>> 1 // 2
0
```
we get 0 instead of 0.5. This is because `//` represents integer division, also
called floor division - if you divide an integer by an integer, you should get
an integer. One way to think about integer division is doing normal division (with decimals),
and then rounding down the result to the nearest integer. So, `7 // 2` gives `3`,
since 7 divided by 2 is 3.5, and we round that down to 3.

If we want the trailing decimals in our division, we canot use `//`. That is because
ints don't support decimals, and int operations should give ints. We need a
different type, with a different operator for that - that type is the float type,
and will be covered next.
