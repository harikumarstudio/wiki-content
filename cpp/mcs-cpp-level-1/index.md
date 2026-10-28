---
title: "C++ Level 1"
description: "Foundations"
authors:
  - harikumarstudio
related:
  - cpp/cs50-scratch
tags:
  - article
---

## Primitive Data Types

```cpp
bool    // true / false  
char    // character 
int     // whole number  
float   // decimal number 
double  // more precise decimal      
void    // no value 
```

1. Boolean - bool 
  - stores either true or false (1 or 0)
  - typically takes 1 byte 
2. Character - char
  - stores a single character ('Z')
3. Integer types: 
  - Short (2 bytes) (`short age = 35;`)
  - Int (4 bytes) (`int score = 100;`)
  - Long (4 or 8 bytes) (`long distance = 10000;`)
  - Long long (8 bytes) (`long long population = 2000000000;`)
4. Floating-point types : 
  - Float (4 bytes) (`float speed = 12.5f;`)
  - Double (8 bytes) (`double price = 19.99;`)
  - Long double (8 bytes/varies by platform) (`long double measurement = 123.456789;`)
5. Void:
  - represents no value (It's commonly used with functions that don't return anything)
```cpp
void sayWelcome
{
	Std::cout << "Welcome!"; 
}  
```
