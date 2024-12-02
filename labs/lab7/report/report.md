---
## Front matter
title: "Отчет по лабораторной работе №7"
subtitle: "Дискретное логарифмирование на конечном поле"
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

Изучить дискретное логарифмирование на конечном поле

# Выполнение лабораторной работы

1. Я реализовал метод Полларда на языке julia.

```julia
function pollard_rho_logarithm(base, target, p)
    # Параметры разбиения
    u = 2  # Первая граница
    v = 2  # Вторая граница

    # Функция отображения f(c)
    function f(c, x, p)
        # Разбиение в зависимости от c
        if c < u
            # Первая ветвь: c < u
            return (base * c) % p, (x + 1) % (p - 1)
        elseif c < v
            # Вторая ветвь: u <= c < v
            return (c * c) % p, (2 * x) % (p - 1)
        else
            # Третья ветвь: c >= v
            return (target * c) % p, (x + 1) % (p - 1)
        end
    end

    # Инициализация переменных
    c, x = 1, 0  # Медленная итерация
    d, y = 1, 0  # Быстрая итерация

    step = 0
    while true
        step += 1

        # Выполняем одну итерацию для c
        c, x = f(c, x, p)

        # Выполняем две итерации для d (ускоренная итерация)
        d, y = f(d, y, p)
        d, y = f(d, y, p)


        # Проверка на совпадение
        if c == d
            if x != y
                # Решение найдено
                solution = (x - y) % (p - 1)
                return solution >= 0 ? solution : solution + (p - 1)
            else
                # Циклическое совпадение без решения
                return "Решение не найдено (циклическое совпадение)."
            end
        end
    end
end
```




    pollard_rho_logarithm (generic function with 1 method)




```julia
# Пример использования алгоритма
p = 107       # Модуль
base = 10     # Основание
target = 64   # Целевое число
result = pollard_rho_logarithm(base, target, p)
println("Результат: x = $result")
```

    Результат: x = 60
    


```julia
result = pollard_rho_logarithm(12, 72, 113)
println("Результат: x = $result")
```

    Результат: x = 56
    


```julia

```


# Выводы

Я реализовал метод Полларда для Дискретного логарифмирования
