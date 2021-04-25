Consider the expression `1 / 0`. What happens if you evaluate it?

If you guessed something along the lines of crashing, infinity, or giving an
undefined result, you'd be on the correct. In math, dividing by zero is
an undefined operation. As such, the designers of Python decided to make
Python crash if you try to divide a number by 0.

```
>>> 1/0
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: division by zero
```

Now, consider the expression `1 / 0 > 2 and 1 > 2`. What do you think will happen when
we evaluate this?

If we actually run this, we see:
```
>>> 1 / 0 > 2 and 1 > 2
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: division by zero
```

As we might expect, Python still crashes when it tries to evaluate it.
This is because when Python evaluates boolean expressions, it evaluates
them from left to right. It reads the expression on the left first and tries
to evaluate it. Since it cannot evaluate 1 / 0, it crashes.

Now, let's make one seemingly small change. What happens if we switch the
order of the booleans in that expression?
```
>>> 1 > 2 and 1 / 0 > 2
False
```
Huh? Python didn't crash anymore. But there's still a dividing by 0 on
the right side of the expression! What happened?

The phenomenon that we are visualizing here is called **short circuiting**.
Under the hood, Python realized that it didn't have to look at both sides
of the boolean expression to determine its value. But how could it do this?

Well, to see this, if we look at all the possible values of `a and b` for two booleans
`a` and `b`,

| `a`     | `b`     | `a and b` |
|---------|---------|-----------|
| `True`  | `True`  | `True`    |
| `True`  | `False` | `False`   |
| `False` | `True`  | `False`   |
| `False` | `False` | `False`   |

If we look at the last two entries in the first and third column, we can see
that whenever `a` evaluates to False, no matter what `b` is, `a and b` *always*
evaluates to False. So, if Python evaluates the left hand side of `a or b` to
False, and sees an `and` in the middle, Python knows that no matter what is on
the right hand side, the answer to the whole expression will be False anyways,
and Python simply stops looking at the right hand side entirely, doesn't
even attempt to evaluate it, and returns False. *That* is why the flipped
version of the above expression did not crash. Since `1 > 2` is False,
Python saw `1 > 2 and ...` and didn't even look at the other side, and gave back False.

Note that we cannot make this same kind of shortcut logic if `a` is True.
In that case, Python has to look at the right hand side of `a and b` in order
to determine whether the result is True or False.

Similarly, if we look at all the possible values of `a or b` for two booleans
`a` and `b`,

| `a`     | `b`     | `a or b` |
|---------|---------|----------|
| `True`  | `True`  | `True`   |
| `True`  | `False` | `True`   |
| `False` | `True`  | `True`   |
| `False` | `False` | `False`  |

we see that if `a` is True, `a or b` is always True no matter what.
So, Python can make this same simplifying assumption, and automatically return
True if `a` is True and the middle operator is `or`, regardless of what is
on the right hand side of the expression. We can see this in action below:

```
>>> (1 / 0 > 2) or (1 < 2)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: division by zero
>>> (1 < 2) or (1 / 0 > 2)
True
```

While the above examples of short-circuiting may seem a bit contrived, we will
see more useful applications of short-circuiting later on.