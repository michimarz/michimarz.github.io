---
layout: post
title: "Function pointers""
author: thomas_schwarz
tags: C
---

## Function pointer

This is a function

```C
int something(char* s);

```

this is also a function:

```C
int (something)(char* s);

```

And this is a variable (that can point to a function with the given signature):

```C
int (*something)(char* s);
```

So we need:\
- an asterisk in front of the name\
- parentheses\
and we get a *function pointer*.


