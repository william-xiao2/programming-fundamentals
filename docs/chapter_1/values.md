# Values

When you type an expression into the Python shell, Python doesn't actually
"do" anything with that value - that is, until you tell it explicitly to do
something with it. You tell it to do something when you hit the enter key
and send the value to Python. When Python gets this expression, it
**evaluates** it, thus turning it into a **value**. Values are what Python
produces after evaluating an expression.

As a real-life reference, when you type a math expression into a calculator
(e.g. 1 + 2), and then you hit the equals key, the calculator then displays 3.
This 3 would be the "value" associated with that expression.

The reason why we distinguish between expressions and values is because
Python can only operate on values. Expressions are a human-friendly way
for programmers to tell Python what values to operate on.
You cannot enter a value yourself. You can only enter expressions.

To see this directly in the Python shell,

```
>>> 42
42
```

The `42` you typed yourself after the >>> would be the expression. After you
hit enter, Python gave you back the number `42`, without the >>> after it.
This second `42` is the value.

Another example:
```
>>> 1 + 2
3
```
The `1 + 2` you typed would be the expression, and the `3` that came after it
after you hit the enter key would the the value. Python took the more complicated
expression, evaluated it (which, in this context, means evaluating the math),
and gave back the resulting value.