# lab04

Лабораторная работа №4 посвящена настройке непрерывной интеграции для CMake-проекта.

В качестве основы используется проект из lab03: статическая библиотека `print` и CMake-сборка.

## Состав проекта

- `CMakeLists.txt` — сборка библиотеки `print` и установка через цель `install`.
- `include/print.hpp` — заголовочный файл библиотеки.
- `sources/print.cpp` — реализация библиотеки.
- `.travis.yml` — конфигурация Travis CI.
- `appveyor.yml` — конфигурация AppVeyor.
- `REPORT.md` — отчет по лабораторной работе.

## Локальная сборка

```sh
cmake -S . -B _build -DCMAKE_INSTALL_PREFIX=_install
cmake --build _build
cmake --build _build --target install
```

## Travis CI

Travis CI должен собирать проект на Linux. По заданию используются компиляторы `gcc` и `clang`.

## AppVeyor

AppVeyor используется для проверки сборки на Windows.

## Ссылка на репозиторий

https://github.com/NorthDakota11/lab4
