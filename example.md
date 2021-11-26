# Defining and declaring a function

In C++, it is possible to define and declare functions in separate files.

## Benefits
Separating definitions from declarations is not strictly necessary, but it does
have a number of benefits. Most notably, it is possible to have more incremental
builds with this approach.

## Definition

To define a function, simply provide the function signature in a header file.

```cpp foo.hpp
#pragma once

#include <string>

int foo(const std::string&, const std::string&);
```

## Declaration

The declaration is the implementation of the function. In a cpp file, provide
the implementation of the function with the same signature as in the header.

```cpp foo.cpp
#include "bar.hpp"

#include <string>

int foo(const std::string& s1, const std::string& s2) {
  return std::stoi(s1) + std::stoi(s2);
}
```

