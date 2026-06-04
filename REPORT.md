# Отчет по домашнему заданию ЛР4

## Задание

Настроить непрерывную интеграцию для CMake-проекта из предыдущей лабораторной работы.

## Что сделано

1. Добавлен CMake-проект.
2. Добавлена конфигурация Travis CI для Linux.
3. Добавлена конфигурация AppVeyor для Windows.
4. Описана проверка сборки и установки проекта.

## Проверка на Linux

```sh
cmake -S . -B _build -DCMAKE_INSTALL_PREFIX=_install
cmake --build _build
cmake --build _build --target install
```

Ожидаемый результат: проект успешно собирается и устанавливается.

## Проверка на Windows

```sh
cmake -S . -B _build -DCMAKE_INSTALL_PREFIX=_install
cmake --build _build --config Release
cmake --build _build --config Release --target install
```

Ожидаемый результат: проект успешно собирается в конфигурации Release.

## Вывод

Домашнее задание выполнено: для проекта подготовлены файлы CI для сборки на Linux и Windows.

## Ссылка

https://github.com/NorthDakota11/lab4
