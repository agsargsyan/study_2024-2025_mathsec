---
## Front matter
title: "Отчет по лабораторной работе №6"
subtitle: "Разложение чисел на множители"
author: "Арам Грачьяевич Саргсян"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Изучить вероятностные алгоритмы проверки чисел на простоту.

# Выполнение лабораторной работы

1. Я реализовал метод Полларда на языке julia.

```julia
using Random
using StatsBase

# Функция для вычисления НОД
function gcd(a::Int, b::Int)
    while b != 0
        a, b = b, a % b
    end
    return a
end

function pollards_rho(n::Int, c::Int, f::Function)
    a = c
    b = c

    while true
        # Вычисление следующего значения a и b
        a = f(a) % n
        b = f(f(b) % n) % n

        # Вычисление НОД
        d = gcd(abs(a - b), n)

        # Проверка условия завершения
        if d > 1 && d < n
            return d  # Нетривиальный делитель найден
        elseif d == n
            return "Делитель не найден"
        end
    end
end

# Пример использования:
n = 1359331  # Число, для которого ищем делитель
c = 1   # Начальное значение
f(x) = x^2 + 5  # Пример сжимающей функции

result = pollards_rho(n, c, f)
println("Найденный делитель: $result")

```

    Найденный делитель: 1181
    

# Выводы

Я реализовал алгоритм разложения чисел на множители.
