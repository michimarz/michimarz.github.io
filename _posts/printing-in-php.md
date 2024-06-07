---
layout: post
title:  "Printing in PHP"
author: michi_marzo
tags: php
---

## Printing in PHP

### echo

Use this mostly.  
It can print multiple values.

```php
echo 'Something ', 123;
```

### print

Never use this one.  
It can't print multiple arguments.

```php
print 'Something';
```

### print_r()

This one is good for printing arrays.

```php
print_r([1,2,3]);
```

### var_dump()

This one prints also a type.

```php
var_dump('Hello');
var_dump(true);
```

Output:

```
string(5) Hello
bool(true)
```

### var_export()

Outputs a string together with quotes.

