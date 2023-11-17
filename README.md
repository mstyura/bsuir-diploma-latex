﻿# Цель
Цель данного проекта покончить с мучениями связанными с оформлением записок к дипломным проектам в соответствии с требованиями [БГУИР](http://bsuir.by).
Способ достижения цели - создание шаблона структуры проекта для LaTeX с преамбулой, настроенной под соблюдение требований к оформлению записок.
Документ в соответствии с которым настраивается оформление документа: [СТАНДАРТ ПРЕДПРИЯТИЯ. ДИПЛОМНЫЕ ПРОЕКТЫ (РАБОТЫ). ОБЩИЕ ТРЕБОВАНИЯ СТП 01—2013](http://www.bsuir.by/m/12_100229_1_80040.pdf).


# Рекомендации
* Рекомендуемый дистрибутив LaTeX для Windows [MiKTeX](http://miktex.org/).
* Рекомендуемый редактор [Sublime Text 2](http://www.sublimetext.com/2) вместе с [менеджером пакетов](http://wbond.net/sublime_packages/package_control) и установленным пакетом [LaTeXTools](https://github.com/SublimeText/LaTeXTools) и PDF просмотрщиком [SumatraPDF](http://blog.kowalczyk.info/software/sumatrapdf/free-pdf-reader.html).
* Рекомендуемые справочные пособия по вопросам связанным с LaTeX: [Bing](http://bing.com/?mkt=en-us), [Google](http://google.com), [Yandex](http://ya.ru) и книги.
* Рекомендуемая программа для ведения библиографической базы данных: [JabRef](http://jabref.sourceforge.net/)
* Инструкция по установке русского Times New Roman из пакета pscyr находится [здесь](http://plumbum-blog.blogspot.com/2010/06/miktex-28-pscyr-04d.html)
* Если возникли **проблемы с pscyr**, то можно переключиться на использование **scalable-cyrfonts-tex**, с которым также могут быть проблемы при установке, но их **проще решить** (см. 
[Wiki→Возникающие-ошибки](https://github.com/mstyura/bsuir-diploma-latex/wiki/Возникающие-ошибки#scalable-cyrfonts-tex-on-ubuntu))

## Установка
### Vagrant
Если у вас возникли проблемы с установкой и настройкой латеха на Windows или Linux, то вы можете воспользоваться виртуальной машиной для vagrant, которая сразу готова к сборке проекта (предполагается использование scalable-cyrfonts-tex, а не pscyr).
- установить vagrant (рекомендуем версию 1.7 или выше)
- зайти в каталог с проектом и выполнить команду `vagrant up` (*дождаться загрузки образа виртуальной машины из сети*)
- выполнить команду `vagrant ssh`
- можно приступить к сборке проекта (команды `make`, `make clean` и т.д.)

### Linux, Ubuntu (TeX Live)
- установить texlive-full: `sudo apt-get install texlive-full`
- установить модифицированный [scalable-cyrfonts-tex (ссылка на скачивание)](https://yadi.sk/d/GW2PhDgEcJH7m): `sudo dpkg -i scalable-cyrfonts-tex-shurph_4.16_all.deb`
- можно приступать к сборке проекта

### Linux, Arch (TeX Live)
- установить make: `sudo pacman -S make`
- установить пакеты texlive: `sudo pacman -S texlive-bin texlive-core texlive-langcyrillic`
- используя [yay](https://github.com/Jguer/yay) поставить из AUR tllocalmgr и texlive-pscyr: `yay -S tllocalmgr texlive-pscyr`
- установить через tllocalmgr sistyle: `tllocalmgr install sistyle`
- можно приступать к сборке

### Windows (MiKTeX)
- см. выше список рекомендаций
- раскомментировать строку `\input{fonts_windows}` в файле `preamble.tex` (и закомментировать строку `\input{fonts_linux}`)


# Пример
В качестве примера приведены моя пояснительная записка к дипломному проекту [example_diploma.pdf](https://github.com/mstyura/bsuir-diploma-latex/blob/master/example_diploma.pdf)
 и преддипломной практике [example_practice.pdf](https://github.com/mstyura/bsuir-diploma-latex/blob/master/example_practice.pdf).

# Дальнейшее развитие
Проект будет развиваться по мере необходимости внесения изменений и обнаружения несоответствий требованиям.
Помощь в доработке шаблона приветствуется.

# Примечание
Многое, наверное, сделано некрасиво и не правильно с точки зрения LaTeX, но я пока новичок и только учусь.
__Первоначальная компиляция проекта может занять некоторое время, т.к. должны установиться пакеты, используемые в preamble.tex__.
Для диагностики неисправности рекомендуется посмотреть генерируемый log файл или запустить компиляцию из командной строки с помощью pdflatex.

# Помощь
Описания назначений файлов можно прочитать в [вики](https://github.com/mstyura/bsuir-diploma-latex/wiki/%D0%9E%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5%20%D1%84%D0%B0%D0%B9%D0%BB%D0%BE%D0%B2).

# UPD
~~После защиты дипломного проекта в качестве примера оформления вместо той каши из букв, которая в примерах сейчас, планирую выложить пояснительную записку от своего дипломного проекта.~~
Сделано.
