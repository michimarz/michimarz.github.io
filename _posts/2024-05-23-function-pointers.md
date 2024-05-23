---
layout: post
title: "Function pointers"
author: michi_marzo
tags: C
---

## Function pointers

This is a function

```c
int something(char* s);

```

this is also a function:

```c
int (something)(char* s);

```

And this is a variable (that can point to a function with the given signature):

```c
int (*something)(char* s);
```

So we need:
- an asterisk in front of the name
- parentheses\
and we get a *function pointer*.


