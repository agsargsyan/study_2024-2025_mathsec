---
## Front matter
lang: ru-RU
title: Презентация по лабораторной работе №7
subtitle: Дискретное логарифмирование в конечном поле
author:
  - Саргсян А. Г.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 1 декабря 2024

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

## Цель работы 

Реализовать предложенный алгоритм программно.

##  Результаты алгоритма Полларда

```julia
# Пример использования алгоритма
p = 107       # Модуль
base = 10     # Основание
target = 64   # Целевое число
result = pollard_rho_logarithm(base, target, p)
println("Результат: x = $result")
```

    Результат: x = 60
    

## Выводы

Я реализовал преложенный алгоритм программно.
