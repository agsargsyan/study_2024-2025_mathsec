---
## Front matter
lang: ru-RU
title: Презентация по лабораторной работе №8
subtitle: Целочисленная арифметика многократной точности
author:
  - Саргсян А. Г.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 7 декабря 2024

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

Реализовать предложенные алгоритмы программно.

1. алогритм сложения
2. алгоритм вычитания
3. алгоритмы умножения
4. алгоритм деления

##  Результаты выполнения алгоритмов

```julia
u, v = [1, 2, 3, 4, 5, 6, 7, 8, 9]   
b = 10          
println("Сложение: ", add(u, v, b))
println("Вычитание: ", subtract(u, v, b))
println("Умножение: ", multiply(u, v, b))
println("Быстрое умножение: ", fast_multiply(u, v, b))
q, r = divide(u, v, b)
println("Деление: q = ", q, ", r = ", r)
```
    Сложение: 246913578
    Вычитание: 0
    Умножение: 15241578750190521
    Быстрое умножение: 15241578750190521
    Деление: q = 1, r = 0
    
## Выводы

Я реализовал преложенный алгоритм программно.
