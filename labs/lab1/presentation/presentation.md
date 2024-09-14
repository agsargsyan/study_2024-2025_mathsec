---
## Front matter
lang: ru-RU
title: Презентация по лабораторной работе №1
subtitle: Шифры простого сдвига
author:
  - Саргсян А. Г.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 14 сентября 2024

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

# Цель работы 

## Цели и задачи работы
Цели:

Познакомиться с шифрами простой замены

Задачи:

- Реализовать шифр Цезаря с произвольным ключом
- Реализовать шифр Атбаш

# Ход работы

## Шифр Цезаря

```
for (int i = 0; i < text.length(); i++) {
            char ch = text.charAt(i);
            if (ch >= 'А' && ch <= 'Я') { // Uppercase Cyrillic
                ch = (char) ((ch - 'А' + key) % 32 + 'А');
            } else if (ch >= 'а' && ch <= 'я') { // Lowercase Cyrillic
                ch = (char) ((ch - 'а' + key) % 32 + 'а');
            }
            result.append(ch);
        }
        return result.toString();
```

## Шифр Атбаш
```
for (int i = 0; i < text.length(); i++) {
            char ch = text.charAt(i);
            int index = ALPHABET.indexOf(ch);
            if (index != -1) {
                char mirroredChar = ALPHABET.charAt(ALPHABET.length() 
				- 1 - index);
                result.append(mirroredChar);
            } else {
                result.append(ch);
            }
        }
        return result.toString();
```
# Выводы

## Выводы

Я познакомился со шифрами сдвига.