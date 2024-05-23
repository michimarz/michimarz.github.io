---
layout: post
title: "Function pointers"
author: michi_marzo
tags: C
---

## Function pointers

This is a function declaration:

```c
int something(char* s);
```

this is also a function declaration:

```c
int (something)(char* s);
```

And this is a variable declaration (this variable can point to a function with this signature):

```c
int (*something)(char* s);
```

So we need:
- an asterisk in front of the name
- parentheses


and we get a **function pointer**.


