# Отчет по лабораторной работе №4

## Тема

Непрерывная интеграция для CMake-проекта.

## Цель работы

Настроить автоматическую сборку проекта на сервисах CI. По заданию Travis CI используется для Linux-сборки, AppVeyor — для Windows-сборки.

## Выполненные действия

1. В репозиторий добавлен CMake-проект с библиотекой `print`.
2. Добавлен файл `.travis.yml` для Travis CI.
3. Добавлен файл `appveyor.yml` для AppVeyor.
4. В CMake добавлена цель установки `install`.

## Основные команды

```sh
cmake -S . -B _build -DCMAKE_INSTALL_PREFIX=_install
cmake --build _build
cmake --build _build --target install
```

## Ожидаемый результат выполнения команд

После выполнения команд создается каталог `_build`, собирается статическая библиотека `print`, затем файлы устанавливаются в каталог `_install`.

Пример результата:

```text
[100%] Built target print
Install the project...
-- Install configuration: ""
```

## Проверка CI

Travis CI должен выполнить сборку проекта на Linux. AppVeyor должен выполнить сборку проекта на Windows.

## Ссылка на репозиторий

https://github.com/NorthDakota11/lab4
