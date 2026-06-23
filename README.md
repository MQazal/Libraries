# 📚 C++ OOP Libraries

A collection of **6 header-only, reusable C++ libraries** built with OOP — designed to be dropped into any C++ project as a personal standard library.

---

## 📦 Libraries

| File | Purpose | Lines |
|---|---|---|
| `clsString.h` | String manipulation & analysis | 612 |
| `clsDate.h` | Date arithmetic & calendar operations | 1036 |
| `clsMyString.h` | Extended string utilities | — |
| `clsInputValidate.h` | Console input validation | — |
| `clsPeriod.h` | Time period calculations | — |
| `clsUtil.h` | General utility helpers | — |

---

## 🔍 Library Details

### 🔤 `clsString.h`
Full-featured string library exposing both **static** and **instance** methods:

- Case conversion — `UpperAllString`, `LowerAllString`, `InvertStringLettersCase`, `UpperFirstLetterOfEachWord`
- Letter analysis — `CountLetters`, `CountVowels`, `PrintVowelCharacters`, `IsVowelCharacter`
- Word operations — `CountWords`, `Split`, `ReverseStringWords`, `ReplaceWordInString`, `JoinStringByVector`
- Text utilities — `Trim`, `TrimFromLeft`, `TrimFromRight`, `RemovePunctuations`, `ReversedCharacters`
- Character search — `CountSpecificLetter`, `CountTimesOfCharacter`, `My_find`
- Custom properties via `__declspec` — `Text`, `Letter`, `delimiterType`
- Built-in `vector<string>` word buffer — `AddWordToVector`, `getWordsOfVector`, `ClearVector`

```cpp
clsString s("hello world", 'l', " ");
s.UpperFirstLetterOfEachWord();  // "Hello World"
s.CountVowels();                 // 3
s.Split();                       // ["hello", "world"]
s.ReverseStringWords();          // "world Hello"
```

---

### 📅 `clsDate.h`
Comprehensive date library — internally uses `clsString.h`:

- Date construction — from `Day/Month/Year`, from string, from day-order-in-year, or from system clock
- Calendar printing — `PrintCalendarOfMonth`, `PrintYearCalendar`
- Date arithmetic — `AddOneDay`, `IncreaseDateByXDays/Weeks/Months/Years/Decades/Centuries`
- Date comparison — `IsDate1BeforeDate2`, `IsDate1EqualDate2`, `IsDate1AfterDate2`, `CompareDates`
- Business logic — `IsBusinessDay`, `IsWeekEnd`, `CalculateBusinessDays`, `CalculateVacationDate`
- Difference calculation — `GetDifferenceInDays`, `GetDifferenceInDaysWithSign`, `CalculateMyAgeInDays`
- Time units — `NumberOfDaysInYear`, `NumberOfHoursInAMonth`, `NumberOfSecondsInYear`
- Remaining time — `DaysUntilEndOfWeek`, `DaysUntilEndOfMonth`, `DaysUntilEndOfYear`
- Leap year — `IsLeapYear`, `NumberOfDaysInYear`
- Custom properties via `__declspec` — `Day`, `Month`, `Year`

```cpp
clsDate today;                          // Auto-loads system date
clsDate d(15, 6, 2025);

d.IncreaseDateByXDays(10);              // 25/6/2025
d.IsLeapYear();                         // false
d.GetDayOrderInWeek();                  // 3 (Wednesday)
d.CalculateBusinessDays(clsDate(1,7,2025)); // business days between dates
d.PrintCalendarOfMonth();               // prints June 2025 calendar
clsDate::GetDifferenceInDays(d1, d2);  // static usage
```

---

## ⚙️ Design Patterns

Every library follows the same consistent design:

- **Dual API** — every method exists as both `static` (pass data in) and instance (uses object's state)
- **`__declspec` properties** — C++-style getters/setters accessed like fields (`obj.Text = "..."`)
- **Cross-library composition** — `clsDate` imports and uses `clsString` internally
- **Header-only** — zero build setup, just `#include` and use

---

## 🚀 Usage

```cpp
#include "clsString.h"
#include "clsDate.h"

// Static usage
clsString::UpperAllString("hello");         // "HELLO"
clsDate::IsLeapYear(2024);                  // true

// Instance usage
clsString s("hello world", 'o', " ");
s.CountVowels();                            // 3

clsDate d(1, 1, 2025);
d.IncreaseDateByOneYear();
d.Print();                                  // 1/1/2026
```

---

## 🛠️ Requirements

- C++11 or later
- MSVC recommended (for `__declspec` property support)
- No external dependencies
