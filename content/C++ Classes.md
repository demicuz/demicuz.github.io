---
title: "C++ Classes"
date: "2023-03-12"
---

If a method doesn't change the object's fields, write `const` in the end:
```c++
class Time {
private:
  int hours;
  int minutes;
  int seconds;

public:
  Time(int h, int m, int s);

  int GetHours() const;
  int GetMinutes() const;
  int GetSeconds() const;
};
```

### Links
- [Классы - Основы С++](https://via.hypothes.is/https://academy.yandex.ru/handbook/cpp/article/classes)