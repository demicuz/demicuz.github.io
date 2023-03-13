---
title: "Python scopes and namespaces"
date: "2023-02-07"
---

[Python Tutorial - scopes and namespaces](https://docs.python.org/3/tutorial/classes.html#tut-scopes)

This stuff is possible:
```Python
if True:
    a = 10

print(a)

for i in range(1):
    wat = "wat"

print(wat)

```

### Footguns
```Python
global_foo = 42

def foo_changer():
    global_foo = 123

foo_changer()
print(global_foo)  # 42
```

`global_foo` here is **not** being assigned. Instead, a local variable is created and assigned. See also `global` and `nonlocal` statements.

> A special quirk of Python is that – if no `global` or `nonlocal` statement is in effect – assignments to names always go into the innermost scope. Assignments do not copy data — they just bind names to objects. The same is true for deletions: the statement `del x` removes the binding of `x` from the namespace referenced by the local scope. In fact, all operations that introduce new names use the local scope: in particular, `import` statements and function definitions bind the module or function name in the local scope.

But you should avoid code like this anyway.