---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №5"
subtitle: "Основы интерфейса взаимодействия пользователя с системой Unix на уровне командной строки"
author: "Матвеева Анастасия Сергеевна"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
;lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Целью данной работы является приобретение  практических  навыков  взаимодействия пользователя с системой посредством командной строки.

# Задачи лабораторной работы

Задачи:

1. Научиться работать с системой с помощью командной строкой
2. Изучить команды cd, pwd, mkdir, rm, rmdir, history

# Выполнение лабораторной работы

1. Переходим в каталог /tmp, используя команду «cd /tmp» и выводим на экран содержимое каталога /tmp, используя команду «ls» с различными опциями (рис. -@fig:001):
 
![Переход в /tmp](image/01.png){ #fig:001 width=70% }

- «ls»− выводится  список каталогов  и  файлов,  которые  можно увидеть, «вручную» открыв каталог tmp
- ls-a»− к  списку,  описанному  в  предыдущем  пункте, добавляются скрытые каталоги и файлы(их имена начинаются с точки)
- «ls-F»−с  помощью  этой  команды  получаеминформацию  о типах файлов
- «ls-l» −получаем список каталогов и файлов, но  уже с  более подробной информацией о них
- «ls-alF»−данная  команда  отобразит  список  всех  каталогов  и файлов, в том числе и скрытых, с подробной информацией о них


2.  Чтобы  определить,  есть  ли  в  каталоге  /var/spool подкаталог  с именем cron, перейдем в указанный каталог с помощью команды «cd /var/spool»,  просмотрим  его  содержимое,  используя  команду  «ls»,и, таким образом,убедимся, что данный подкаталог существует. Далее  перехожу  в  свой  домашний  каталог  с  помощью  команды «cd ~» и,  используя  команду  «ls -alF»,  вывожу  на  экран  его содержимое. Видно, что владельцем всех каталогов и файлов, кроме родительского каталога (его владелец пользователь root из  группы  пользователей root),является  пользователь asmatveeva из группы пользователей studsci.(рис. -@fig:002)

![Перехожу в каталог /var/spool, убеждаюсь, что он существует, и далее перехожу в ~ и просматриваю владельцев всех каталогов и файлов](image/02.png){ #fig:002 width=70% }

3. В  домашнем  каталоге  создаем  новый  каталог newdir,  используя команду «mkdir newdir». Убеждаемся, что каталог создан, с помощью команды «ls». Командой «cd newdir» переходим в ранее созданный каталог и там создаем каталог morefun, используя команду «mkdir morefun». Командой «ls» проверяем правильность выполненных действий (рис. -@fig:003).

![Создаю каталог newdir и подкаталог morefun](image/03.png){ #fig:003 width=70% }

4. Используя  команду  «mkdir letters memos misk»,создаем  в домашнем  каталоге  три  новых (рис. -@fig:004).  Далее  с  помощью  команды  «rm –r letters memos misk» удаляем  созданные  каталоги. Командой «ls» проверяем правильность выполненных действий (рис. -@fig:005).

![Создаю каталоги  letters, memos, misk](image/04.png){ #fig:004 width=70% }

![Удаляю каталоги letters, memos, misk](image/05.png){ #fig:005 width=70% }

5. Пробуем удалить каталог newdir командой «rm newdir». Получаем отказ  в  выполнении  команды  (т.к.  данный  каталог  содержит подкаталог morefun и требуется при удалении использовать опцию -r). Удаляем  каталог newdir/morefun,  используя команду  «rm –r newdir/morefun».Командой «ls» проверяем правильность выполненного действия (рис. -@fig:006).

![Удаляю каталог newdir](image/06.png){ #fig:006 width=70% }

6. Используя  команду  «man ls»,  определяю,  какую  опцию  команды ls необходимо  использовать,  чтобы  просмотреть  содержимое  не  только указанного каталога, но и подкаталогов, входящих в него (рис. -@fig:007).

![Определяю,  какую  опцию  команды ls необходимо  использовать,  чтобы  просмотреть  содержимое  не  только указанного каталога, но и подкаталогов, входящих в него](image/07.png){ #fig:007 width=70% }

7. Используя то же руководство по команде «ls», открытое в предыдущем пункте,   определяю   набор   опций   команды ls,   позволяющий отсортировать  по  времени  последнего  изменения  выводимый  список содержимого каталога с развернутым описанием файлов (рис. -@fig:008, -@fig:009, -@fig:010).

![Опции команды ls](image/08.png){ #fig:008 width=70% }

![Опции команды ls](image/09.png){ #fig:009 width=70% }

![Опции команды ls](image/10.png){ #fig:010 width=70% }

8. Используя команды «man cd», «man pwd», «man mkdir», «man rmdir», «man rm», просматриваю описание соответствующих команд(рис. -@fig:011).

![Использую команды man cd, man pwd, man mkdir, man rmdir, man rm](image/11.png){ #fig:011 width=70% }

9. Команда cd (рис. -@fig:012)

![Команда cd](image/12.png){ #fig:012 width=70% }

Заметим, что данная команда не имеет дополнительных опций.
 
10. Команда pwd (рис. -@fig:013):

![Команда pwd](image/13.png){ #fig:013 width=70% } 

- -L, --logicalне разыменовывать символические ссылки. Если путь содержит символические  ссылки,  то  выводить  их  безпреобразования  в исходный путь;
- -P, --physical преобразовывать (отбрасывать    символические    ссылки) символические ссылки в исходные имена. Если путь содержит символические ссылки, то они будут преобразованы в названия исходных директорий, на которые они указывают;
- --help показать справку по команде pwd;
- --version показать версию утилиты pwd.

11. Команда mkdir (рис. -@fig:014):
 
![Команда mkdir](image/14.png){ #fig:014 width=70% }
 
- -m,--mode=MODE устанавливает  права  доступа  для  создаваемой  директории. Синтаксис MODE такой же как у команды chmod;
- -p,--parents создать  все  директории,  которые  указаны  внутри  пути.  Если какая-либо директория существует, то предупреждение об этом не выводится;
- -v, --verbose выводить сообщение о каждой создаваемой директории;
- -z установить  контекст  SELinux  для  создаваемой  директории  по умолчанию;
- --context[=CTX] установить  контекст  SELinux  для  создаваемой  директории  в значение CTX;
- --help показать справку по команде mkdir;
- --version показать версию утилиты mkdi.

12. Команда rmdir (рис. -@fig:015):

![Команда rmdir](image/15.png){ #fig:015 width=70% }
 
- --ignore-fail-on-non-empty игнорировать директории, которые содержат в себе файлы;
- -p, --parents в  этой  опции  каждый  аргумент  каталога  обрабатывается  как путь, из которого будут удалены все компоненты, если они уже пусты, начиная с последнего компонента;
- -v, --verbose отображение    подробной    информациидля    каждого обрабатываемого каталога;
- --help показать справку по команде rmdir;
- --version показать версию утилиты rmdir

13. Команда rm (рис. -@fig:016):

![Команда rm](image/16.png){ #fig:016 width=70% }

- -f, --force игнорировать несуществующие файлы и аргументы. Никогда не выдавать запросы на подтверждение удаления;
- -i выводить запрос на подтверждение удаления каждого файла;
- -I выдать  один  запрос  на  подтверждение  удаления  всех  файлов, если  удаляется  больше  трех  файлов  или  используется рекурсивное   удаление.   Опция   применяется,   как   более «щадящая» версия опции –i;
- --interactive[=WHEN] вместо WHENможно использовать:never —никогда  не  выдавать  запросы  на  подтверждение удаления.once —выводить запрос один раз (аналог опции -I).
always —выводить запрос всегда (аналог опции -i).Если значение КОГДА не задано, то используется always;
- --one-file-system во  время  рекурсивного  удаления  пропускать  директории, которые находятся на других файловых системах;
- --no-preserve-root если в качестве директории для удаления задан корневой раздел /, то считать, что это обычная директория и начать выполнять удаление;
- --preserve-root[=all] если в качестве директории для удаления задан корневой раздел /, то запретить выполнять команду rm над корневым разделом. Данное поведение используется по умолчанию;
- -r, -R, --recursive удаление директорий и их содержимого. Рекурсивное удаление;
- -d, --dir удалять пустые директории;
- -v, --verbose выводитьинформацию об удаляемых файлах;
- --help показать справку по команде rm;
- --version показать версию утилиты rm.

14. Выведем историю команд с помощью команды «history» (рис. -@fig:017). Далее,  используя  команды,  «!509:s/morefun/morefun01» и  «!510», выполним  команды  509  и  510  (в  509 будет cоздан  каталог morefun1 вместо morefun) (рис. -@fig:018). 

![Команда history ](image/17.png){ #fig:017 width=70% }

![Создаю  каталог morefun1 вместо morefun](image/18.png){ #fig:018 width=70% }

# Выводы

Мы приобрели практические навыки взаимодействия с системой посредством командной строки.

# Ответы на контрольные вопросы

1. Командная строка–специальная  программа, позволяющая  управлять операционной  системой  при  помощи  текстовых  команд,  вводимых  в окне приложения.
2. Для определения абсолютного пути к текущему каталогу используется команда  pwd  (print  working  directory).  Например,  команда  «pwd»  в моем домашнем каталоге выведет: /home/asmatveeva
3. Команда  «ls-F» (или  «ls-aF»,  тогда  появятся  еще  скрытые  файлы) выведет имена файлов в текущем каталоге и их типы. Тип каталога обозначается /, тип исполняемого файла обозначается *, тип ссылки обозначается @.
4. Имена  скрытых  файлов  начинаются  с  точки.  Эти  файлы  в операционной системе скрыты от просмотра и обычно используются для  настройки  рабочей  среды.  Для  того,  чтобы  отобразить  имена скрытых файлов, необходимо использовать команду «ls –a».
5. Команда  rm  используется  для  удаления  файлов  и/или  каталогов. Команда rm-i выдает  запрос  подтверждения  наудаление  файла. Команда rm-r необходима, чтобы удалить каталог, содержащий файлы. Без указания этой опции команда не будет выполняться. Если каталог пуст,  то  можно  воспользоваться  командой  rmdir.  Если  удаляемый каталог  содержит  файлы,  то  команда  не  будетвыполнена –нужно использовать «rm -r имя_каталога». Таким  образом,  каталог,  не  содержащий  файлов,  можно  удалить  и командой rm, и командой rmdir. Файл командой rmdir удалить нельзя.
6. Чтобы  определить,  какие  команды  выполнил  пользователь  в  сеансе работы, необходимо воспользоваться командой «history».
7. Чтобы  исправить  илизапустить  на  выполнение  команду,  которую пользователь уже использовал в сеансе работы, необходимо: 
в первом случае:воспользоваться конструкцией !<номер_команды>:s/<что_меняем>/<на_что_меняем>,   во   втором случае: !<номер_команды>. 
8. Чтобы записать в одной строке несколько команд, необходимо между ними поставить ; . Например, «cd /tmp; ls».
9. Символ  обратного  слэша \ позволяет  использовать  управляющие символы  (".",  "/",  "$",  "*",  "[",  "]",  "^",  "&")  без  их  интерпретации командной оболочкой; процедура  добавления данного  символа  перед управляющими  символами  называетсяэкранированием  символов.Например,  команда  «lsnewdir\/morefun»  отобразит  содержимое каталога newdir/morefun.
10. Команда «ls -l» отображает список каталогов и файлов с подробной информацией  о  них (тип  файла,  право  доступа, число  ссылок, владелец, размер, дата последней ревизии, имя файла или каталога).
11. Полный, абсолютный путь от корня файловой системы –этот путь начинается от корня "/" и описывает весь путь к файлуили каталогу; Относительный  путь–это  путь  к файлу  относительно  текущего каталога(каталога,  где  находится  пользователь). Например, «cd/newdir/morefun»–абсолютный  путь,  «cdnewdir»–относительный путь.
12. Чтобы получить необходимую информацию о команде, необходимо воспользоваться конструкцией man[имя_команды], либо использовать опцию help, которая предусмотрена для некоторых команд.
13. Для автоматического дополнения вводимых команд служит клавиша Tab.
