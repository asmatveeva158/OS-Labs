---
## Front matter
lang: ru-RU
title: Лабораторная работа №13
author: |
	Матвеева Анастасия Сергеевна НПМбд-02-20\inst{1}
institute: |
	\inst{1}RUDN University, Moscow, Russian Federation
date: 3 июня, 2021, Москва, Россия

## Formatting
toc: false
slide_level: 2
theme: metropolis
header-includes: 
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
aspectratio: 43
section-titles: true
---

## Цель работы

Изучить основы программирования в оболочке ОС UNIX. Научится  писать  более  сложные командные  файлы  с  использованием логических управляющих конструкций и циклов.

## Задачи

1. Познакомиться с логическими управляющими конструкций и циклов.
2. В ходе работы написать 3 командных файла.

## Выполнение лабораторной работы

Предварительно для командных файлов создаем файл и открываем emacs. Первый скрипт реализует упрощенный механизм семафора. (рис. -@fig:001) 

![Проверка работы скрипта](image/02.png){ #fig:001 width=70% }

## Выполнение лабораторной работы

Второй командный файл реализовывал команду man. Мы предварительно изучили содержимое каталога /usr/share/man/man1. Командный файл должен в виде результата выдавать справку об этой команде или сообщение об отсутствии справки. (рис. -@fig:002)

![Второй скрипт](image/07.png){ #fig:002 width=70% }

## Выполнение лабораторной работы

Третий командный файл, используя встроенную переменную $RANDOM, генерирует случайную последовательность латинских букв. (рис. -@fig:003)

![Проверка работы скрипта](image/10.png){ #fig:003 width=70% }

## Вывод

В  ходе  выполнения  данной  лабораторной  работы  я  изучила основы программирования в оболочке ОС UNIX и научилась писать более сложные командные файлы с использованием логических управляющих конструкций и циклов.

