---
date: 2014-09-30T00:00:00Z
title: Обеспечение качества данных в проекте OpenStreetMap
tags: ["opensource", "interview", "openstreetmap"]
url: /2014/09/30/quality-assurance-in-openstreetmap.html
---

<img src="/images/logo-openstreetmap.png" alt="OpenStreetMap" style="float:left">

[OpenStreetMap](https://www.openstreetmap.org) - это проект по созданию
картографических данных под свободной лицензией.

Я попросил одного из участников проекта [Илью Зверева](http://ilya.zverev.info)
рассказать о том, чем обеспечивается качество в проекте.

**Расскажи немного о себе.**

Я программист, участник OpenStreetMap и редактор новостного блога [ШТОСМ](http://shtosm.ru)
— так обычно отвечаю. Живу в Петербурге и жалею,
что все активные люди переезжают в Москву.

**Как ты узнал про проект OpenStreetMap и почему он тебя заинтересовал?**

В мае 2010 года собирались на велопокатушку по восточной Финляндии
(для петербуржцев это обычное дело), и я искал бесплатные карты для гармина.
Нашёл где-то пять вариантов, самым приличным из них были карты на основе OSM.
Вернувшись, захотел добавить пару проездов, которых не было на карте.
Так и втянулся. Через месяц напечатал первые обходные листы, и так далее, и так далее.

Мне очень понравилось сообщество. Не с самого начала, конечно:
когда я начал править район, в котором живу, сразу набежали «старички»
и так отругали, что я на полгода забыл про Ленинградскую область вообще,
ушёл поднимать Псковскую. Но всеобъемлющесть проекта OpenStreetMap
привлекает в сообщество людей с разнообразными интересами,
с огромным разбросом точек зрения, и позволяет им участвовать любым способом:
от простого картирования до программирования и написания текстов.
Это сравнимо, наверное, только с сообществом Фидо конца девяностых.

**В проекте участвует _очень_ много людей (на декабрь 2011 года это было
более 900,000 волонтёров). Как получается всей этой массой управлять,
чтобы на выходе получать качественные данные, которые могут использовать
не только обычные люди, но и компании (Apple, MapsWithMe, Foursquare etc).**

Прежде всего, количество зарегистрированных участников (1,8 млн на сегодня)
ни о чём не говорит: из них, наверное, спамеров минимум половина.
335 тысяч участников, сделавших хоть одну правку, 22 тысячи в России
— более полезное число. К сожалению, в OSM слишком большой порог участия,
поэтому непросто определить, кого  можно считать участников, а кто мимо проходил.

Управлять волонтёрами почти невозможно: у них нет ответственности.
Но помогает присущие большинству (и почти поголовно — участникам проекта)
желание упорядочить окружающий мир и желание иметь цель. Первое приводит
к красивым картам, где назначение каждой линии понятно из контекста.
Если осмер видит некрасивую дорогу или пустой квартал — его первым желанием
будет поправить ситуацию. Второе помогает компаниям, использующим данные:
многие участники проекта рисуют с каким-то представлением о назначении данных.
Например, дороги рисуются не просто так, а для навигаторов,
и по ним должны хорошо строиться маршруты, с учётом важности, ограничений, покрытия.
Нередки участники, которые правят карту специально для улучшения выгрузок
в навител или гармин.

Мы делаем карты для себя, то есть, для программ, которыми мы,
те самые обычные люди, пользуемся. Но нас сотни тысяч, и отдельные усилия
сложились в однородную и удобную для использования карту.

**Каким образом люди попадают в проект? Кто-то специально занимается
их привлечением?**

Чаще всего люди попадают случайно, или после упоминания проекта
в каком-нибудь популярном блоге или передаче. Последнее, увы,
случается очень редко: раз-два в год. Привлечением людей никто не занимается,
полгода назад у нас была рабочая группа на этот счёт, но распалась.
Основной механизм всё тот же: человек скачивает карту на навигатор,
видит неточность, идёт на сайт поправить, залипает. Соответственно,
единственный понятный нам способ привлечения — распространить карту
как можно шире. Недавний переход на OpenStreetMap крупных проектов:
Вконтакте, Спутник, 2ГИС — серьёзный шаг в этом направлении.
Хотя оказалось, что большинство людей предпочитают пожаловаться,
но не добавить недостающий адрес своего дома.

**Как получается обеспечивать качество данных? Может есть метрики
для оценки качества данных?**

Качество данных — это абстрактный термин, каждый определяет его по-своему.
Например, для организаций качество равно количеству. Для отдельный
людей качество — это когда обозначен их дом и ближайший магазин.
Для посетителя сайта osm.org качество — когда важные дороги хорошо видны,
а населённые пункты обозначены. Программист качество данных определяет
удобством формата данных и API. По каждому из этих пунктов ситуация печальна,
но достаточно хороша, чтобы OpenStreetMap-ом пользовались.

**Есть ли какие-то инструменты для выявления ошибок на картах?**

Конечно, некоторые аспекты качества можно измерить, или хотя бы отобразить
достаточно наглядно для визуальной оценки. Русское сообщество интересно тем,
что создало огромное количество валидаторов для всех аспектов карты
— в этом его догоняют только французы с их Osmose. Только для контроля состава
и правильности административных границ и населённых пунктов у нас,
кажется, три разных валидатора, в том числе на основе классификаторов
[ОКАТО](https://ru.wikipedia.org/wiki/Общероссийский_классификатор_объектов_административно-территориального_деления),
[ОКТМО](https://ru.wikipedia.org/wiki/Общероссийский_классификатор_территорий_муниципальных_образований)
и [ФИАС](https://ru.wikipedia.org/wiki/ФИАС). Два валидатора контролируют
состав и связность дорожной сети. Также мы проверяем связность
и станции железных дорог, адресацию, названия улиц,
сетевые магазины и прочие заведения, вроде Сбербанка, корректность сложных
структур данных, вроде мультиполигонов, и ещё много чего.

Западные участники сделали несколько валидаторов, покрывающих весь мир.
Самый известный — Keep Right с почти полусотней проверок.
Из последнего — немец Петер Барт месяц назад сделал валидатор направления
течения рек по модели рельефа SRTM, 10 сентября добавил в него
данные для всей планеты. Этот валидатор — часть «игры» [MapRoulette](http://maproulette.org),
где участникам выдаётся одна ошибка за раз, и её нужно поправить,
или сообщить, что проблемы нет. В таком формате ошибки исправлять проще,
потому что есть цель, нет проблемы конфликта правок, и фронт работ
кажется не таким высоким, как в простом списке из десяти тысяч ошибок.

**Есть какие-то меры противодействия вандализму?**

Каждый вандализм особенный, и противодействие различно.
Главное в борьбе с вандализмом — своевременное отслеживание
злонамеренных (или случайно ошибочных) правок. Для этого
есть сервис Who Did It и ежедневно обновляющиеся валидаторы.
Стоит заметить, что к проблемным правкам относятся и хорошие на вид,
но в которых маппер обрисовал запрещённые к использованию снимки
или карты: например, яндекс. Их сейчас можно определить лишь на глаз,
хотя до апреля работал «Вахтёр», который следил за новыми
мелкими объектами в местах, где их нельзя добавить по разрешённым источникам.

Как и в википедии, почти единственный инструмент в работе
с нежелательным правками — reverter, плагин для JOSM и
почти единственный способ отката правки. Увы, у нас пока нет
удобной кнопки «undo», как в вики, потому что откат почти всегда
сопряжён с разрешением конфликтов правок. Но ещё до применения reverter-а
обязательно нужно связаться с автором правки и разобраться,
случайно или специально допущена ошибка. Высокий порог входа в OSM
означает не только малое количество настоящих вандалов (куда проще
вписать туалетную шутку в викистатью, чем нарисовать половой орган на карте),
но и постоянные ошибки со стороны новичков, не успевших прочитать десятки статей,
тем на форуме и учебников.

---------------------------------------

Если вы хотите тоже принять участие в создании карт для OpenStreetMap,
то [эта страница](http://openstreetmap.ru/about/dev)
будет хорошей отправной точкой.

**Дополнительная информация**

- [Beyond good enough? Spatial Data Quality and OpenStreetMap data](https://www.slideshare.net/mukih/beyond-good-enough-spatial-data-quality-and-openstreetmap-data)
- [OpenStreetMap Data Quality](https://www.slideshare.net/geomantic/openstreetmap-data-quality)
- [Quality Assurance Tools script](https://wiki.openstreetmap.org/wiki/Quality_Assurance_Tools_script)
- [OSM Wiki: Quality assurance](https://wiki.openstreetmap.org/wiki/Quality_assurance)
- [Инструменты контроля качества](http://osm.amdmi3.ru)
<!-- Проект [OpenStreetBugs](https://wiki.openstreetmap.org/wiki/OpenStreetBugs) -->
- [Notes](https://wiki.openstreetmap.org/wiki/Notes) - инструмент для сообщения о неточностях на карте

Fin
