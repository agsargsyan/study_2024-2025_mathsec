---
## Front matter
title: "Отчет по лабораторной работе №5"
subtitle: "Вероятностные алгоритмы проверки чисел на чистоту"
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

1. Я реализовал тест Ферма на языке julia (рис. [-@fig:001]).

![Тест Ферма](image/l5_1.png){#fig:001 width=70%}

2. Я реализовал алгоритм вычисления символа Якоби на julia (рис. [-@fig:002]).

![Символ Якоби](image/l5_2.png){#fig:002 width=70%}

3. Я реализовал тест Соловэя-Штрассена на языке julia (рис. [-@fig:003]).

![Тест Соловэя-Штрассена](image/l5_3.png){#fig:003 width=70%}

4. Я реализовал тест Миллера-Рабина на языке julia

![Тест Миллера-Рабина](image/l5_4.png){#fig:004 width=70%}

# Выводы

Я реализовал алгоритмы вычисления числа на простоту на языке julia.
