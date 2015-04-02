---
layout: post
title: Качество кода в Гугл
---

Инженеры и интерны из Google [рассказывают](https://www.quora.com/What-is-the-code-quality-at-Google-like)
о мерах, принимаемых в компании для написания качественного кода.
Некоторые из них утверждают, что качество кода в Google лучше,
чем в Microsoft и Facebook. Они упоминают:

* жёсткое следование стандартам кодирования, описанным в [Google style guides](https://code.google.com/p/google-styleguide/);
* активное ревью кода;
* группы обсуждения "code health";
* отсутствие жёстких сроков выполнения работы, что позволяет выполнять работу правильно,
а не кое-как, чтобы успеть к сроку;
* использование таких штук как "Fixits". Смысл заключается в том, что
любой инженер может предложить изменение кода (например избавление от устаревшего класса во всем проекте)
и предложить организовать Fixit для этих изменений. Когда приходит время
этого Fixit, то все вносят предложенные изменения в свой код и тем самым избавляются от
устаревшего класса во всей кодовой базе;
* распространена культура тестирования: покрытие юнит-тестами очень близко к 100%,
активно используется техники непрерывной сборки, интеграции и тестирования,
а также известные постеры в комнатах отдыха из серии "Testing on the Toilet"
(см. серию постов на эту тему в блоге [Google Testing Blog](http://googletesting.blogspot.ru/search/label/TotT));

Fin