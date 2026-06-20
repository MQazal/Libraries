# OOP-Libraries
Libraries implemented using Object-Oriented Programming (OOP).

# OOP Libraries

A collection of reusable **C++** utility libraries built with **OOP**.

## About

Each library is a self-contained header file (`.h`) that can be dropped into any C++ project — no compilation needed, just `#include` and use.

## Libraries

| File | Description |
|---|---|
| `clsString.h` | String manipulation — case conversion, split, trim, search, count |
| `clsDate.h` | Date & time operations — formatting, calculations, system date |
| `clsPeriod.h` | Period/duration handling between two dates |
| `clsInputValidate.h` | Input validation — type checking, range and format validation |
| `clsMyString.h` | Extended string utilities |
| `clsUtil.h` | General-purpose utility functions |

## Usage

```cpp
#include "clsString.h"

string result = clsString::UpperAllString("hello world"); // "HELLO WORLD"

vector<string> words = clsString::Split("one,two,three", ","); // ["one", "two", "three"]

cout << clsString::CountVowels("Hello World") << endl; // 3
```

## Tech Stack
Language: C++
Paradigm: OOP
Standard Libraries: <string> · <vector> · <cctype> · <iomanip>
- **Language:** C++
- **Paradigm:** OOP
- **Standard Libraries:** `<string>` · `<vector>` · `<cctype>` · `<iomanip>`
