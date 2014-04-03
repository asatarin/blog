---
layout: post
title: Автоматическая генерация генеалогического дерева
---

{{ page.title }}
================

<p class="meta">3 апреля 2014 - Москва</p>

В наше время составление своей родословной является довольно популярным занятием.
Возможно это происходит в силу б*о*льшей доступности государственных архивов
для обычных людей, сайтов, подобных [ОБД Мемориал](http://www.obd-memorial.ru)
или [Подвиг народа](http://www.podvignaroda.ru),
а может и потому, что люди просто стали интересоваться историей своих корней.
Увлекла эта тема и меня.

Мой брат в школьные годы опросил всех, оставшихся вживых, родственников и
на основе этой информации составил генеалогическое дерево до 4-го колена
(так мы узнали, что один из родственников участвовал в Отечественной войне 1812 года),
а потом изобразил его на большом листе ватмана прямоугольниками с ФИО каждого родственника
и стрелками между ними.

Спустя десят лет я в свою очередь решил [продолжить](http://juick.com/estet/521112)
начатое и стал дальше уточнять родословную. Количество родственников выросло
до 50 человек и нужно было перерисовать генеалогическое дерево.
Но в силу своей природной лени я не испытывал желания делать это вручную,
тем более, что перерисовывать его нужно периодически, по мере обновления данных.
Нужно было найти инструмент, который бы на основе данных рисовал граф связей
(а генеалогическое дерево ни что иное как граф) автоматически. Решение было найдено
в виде утилиты *dot* из пакета [graphviz](http://www.graphviz.org). Утилита позволяет на основе
файла, описывающего связи между элементами, получать картинку с графом.
В целом задача была решена и описав связи в файле в таком виде:

```
digraph G {
        rankdir=LR;
        ranksep=.75;
        node [color=grey, style="rounded", shape=box];
        node [fontname="Verdana", size="30, 30"];
        "Линус Торвальдс" -> "Нильс Турвальдс";
        "Линус Торвальдс" -> "Анна Турвальдс";
}
```

можно получить такой граф:

<img src="/images/lifeline-torvalds.png" alt="Семья Торвальдс">

Несмотря на понятный формат файла, поддерживать его для большого количества человек
затруднительно и нужно было придумать способ автоматической
генерации этого файла из какой-нибудь базы данных о родственниках.

Я стал глубже разбираться в этой теме и попробовал найти решения, которые используют
другие, но на тот момент поиск не увенчался успехом. Но после чтения тематических сайтов
я сделал два полезных вывода:

1. в среде профессиональных генеалогов принято информацию о каждом родственнике систематизировать
и хранить в виде, так называемых, генеалогических карточек. Их формат никак не фиксирован,
вы можете его изменять в зависимости от количества информации.
Например:

	* ФИО
	* дата и место рождения
	* дата и место смерти
	* ФИО супруга (супруги)
	* национальность
	* образование
	* дети

2. cтандарт де-факто для хранения информации о родственниках это формат
[GEDCOM](http://en.wikipedia.org/wiki/GEDCOM).
Вот как выглядит одна запись:

```
0 @I1@ INDI
1 NAME Линус /Торвальдс/
1 BIRT
2 DATE 28 DEC 1969
2 SOUR @S1@
3 DATA
4 TEXT Написал первую версию операционной системы Linux.
3 NOTE Спорил с профессорами в юном возрасте.
```

То есть мне нужно было найти приложение, которое бы позволяло хранить такие карточки
и связи между ними и иметь поддержку формата GEDCOM.

Таким  приложением для меня стало [lifelines](http://lifelines.sourceforge.net).
Приложение на первый взгляд выглядит по-спартански, но вся сила
этого приложения в поддержке
[специального языка](http://lifelines.sourceforge.net/manual.3.0.39/ll-reportmanual.html),
на котором можно создавать отчёты и вдобавок оно поддерживает формат GEDCOM для экспорта
и импорта данных.

С помощью скриптов для lifelines я автоматически обновляю генеалогическое дерево
и создаю исходный файл для электронной книги с описанием каждого родственника, который потом
можно скопилировать в TeX в PDF. А при наличии фантазии можно много чего ещё придумать :)

**DISCLAIMER:** К слову, сейчас достаточно много программ, которые всё сделают автоматически.
Это и локальные программы, например [Gramps](https://gramps-project.org),
и онлайн сервисы наподобие [Ancestry](http://www.ancestry.com).
Но на тот момент я или не знал об этих программах или их ещё не было.