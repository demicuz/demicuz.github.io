---
title: "C++ learning log"
date: "2023-03-05"
---

- [[std vector]]
- [[std string]]
- [[C++ Algorithm library]]
- [[C++ Classes]]

### Various notes
```c++
for (size_t i = 0; i != data.size(); ++i) {
    std::cout << data[i] << " ";
}
```

> Это каноническая форма записи такого цикла: в ней принято использовать сравнение `!=` и префиксный `++i.` Для целых чисел не будет разницы, если написать это как-то иначе (например, через `<` и постфиксный `i++`), но потом, когда вы будете писать аналогичные циклы для итераторов других контейнеров, разница появится. Давайте привыкнем всегда оформлять цикл по индексам так.

Пачиму?

`std::getline(std::cin, line)` doesn't skip empty lines, just `std::cin` does.

copy elision

What is `RandomAccessIterator` and how iterators work in C++ in general?

You can define functions in structs:
```c++
struct Date {
  int year = 1970;
  int month = 12;
  int day = 1;

  // could also use std::tie
  bool operator<(const Date& rhs) const {
    if (year != rhs.year) {
      return year < rhs.year;
    }
    if (month != rhs.month) {
      return month < rhs.month;
    }
    return day < rhs.day;
  }
};
```


There is `std::string_view`, which is pretty cool.

- [Move semantics](https://stackoverflow.com/questions/3106110/)
- [Copy and Swap idiom](https://stackoverflow.com/questions/3279543/)