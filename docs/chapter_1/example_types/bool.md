# Type `bool`

The `bool` type refers to logical statements. There are only two boolean
values, and those are `True` and `False`. The term `bool` is short for `boolean`,
a name derived from George Boole, whose work sets the foundation for truth and logic.

{% hint style="hint" %}
Notice how the `True` and `False` are capitalized. This is important.
Python, and programming languages in general, are very picky about capitalization,
among other things. If you type in these values as `true` or `false`, Python
will complain that it doesn't know what you're talking about.
{% endhint %}

The main operations on booleans are:
| Operation | Result                                                                                             |
|-----------|----------------------------------------------------------------------------------------------------|
| `not b`   | Flips the boolean - evaluates to True if `b` is False, and evaluates to False if `b` is True.      |
| `a and b` | Evaluates to True if both `a` and `b` evaluate to True, otherwise, evaluates to False.             |
| `a or b`  | Evaluates to True if at least one of `a` and `b` evaluates to True, otherwise, evaluates to False. |

The `and` and `or` operators work similarly to how they do in the English language.

For example, let's say `a` referred to whether the statement "She gave me an apple"
was true or false, and `b` referred to whether the statement "She gave me a banana"
was true or false.

Then, `a and b` would correspond to the answer to the question "Did she give me both an apple and a banana"?
The only way for this to be true if she gave me both fruits. If she gave me only an apple,
then `b` does not evaluate to True, so she couldn't have given me both, so `a and b` evaluates to False,
since the right hand side is False. And if she gave me neither an apple nor a banana,
then both `a` and `b` evaluate to False, so the entire expression is False.

Similarly, for `a or b`, it would correspond to the question "Did she give me either an apple or a banana"?
and the answer to this question would be whether she gave me at least one of those two fruits.
If she gave me both an apple and a banana, then `a` and `b` would both be true, so
`a or b` would be true. If she gave me just a banana, then `b` would be true, but `a` would not.
However, she still gave me a banana, so she did give me one of an apple or a banana, so
`a or b` is true. If she gave me neither, then she didn't give me either an apple or a
banana, so `a or b` would evaluate to False.

Booleans most often come from comparisons.

These comparison include:
| Operator | Comparison               | Example |
|----------|--------------------------|---------|
| `<`      | Less than                | 1 < 2   |
| `<=`     | Less than or equal to    | 1 <= 2  |
| `>`      | Greater than             | 1 > 2   |
| `>=`     | Greater than or equal to | 1 >= 2  |
| `==`     | Equals                   | 1 == 2  |
| `!=`     | Not equals               | 1 != 2  |

{% hint style="hint" %}
Note how equality comparison uses two equals signs instead of one. One equals
sign means something else, which we will get into in the next lesson.
{% endhint %}

{% hint style="warning" %}
Recall from the previous section on floats that floats are inexact. This means
that comparing two floats with == directly is dangerous. To see an example,
try out `0.1 + 0.2 == 0.3` in the Python shell.
{% endhint %}

These comparisons can be combined with the above operators to make more complex expressions.

For example,

```
(1 < 2) and (3 != 3)
```

simplifies into
```
True and False
```

which further simplifies into
```
False
```

We will see many more examples and uses of boolean logic when we cover if-statements.