---
date: 2016-11-15T00:00:00Z
title: Хитрости в работе с почтовыми рассылками
tags: ["opensource", "productivity", "openbsd"]
---

Если вы участвуете в открытом проекте или просто следите за его жизнью, то
наверняка вы подписаны на почтовую рассылку этого проекта. У меня есть не только
опыт подписчика, но и администратора рассылок. На основе этого опыта я расскажу
про несколько хитростей, о которых многие не знают.  Самые популярные
инструменты для создания почтовой рассылки это Majordomo и Mailman. Первые два
совета подходят обоим, третий я проверял только с Majordomo.

### Хочу следить за проектом без ежедневной горы писем

Вы решили подписаться на рассылку, но каждый день приходит по десятку (а то и
больше писем) и вы на них отвлекаетесь. Некоторые раскладывают письма по разным
папкам и смотрят в эти папки когда есть необходимость (или время). Мне такой
вариант не подходит, у меня вся почта приходит в INBOX и там я её или читаю или
удаляю. Если я буду раскладывать по папкам, то такие письма я не прочитаю
никогда. Для таких случаев удобно использовать ежедневные дайджесты со списком
обсуждений. Вы будете в курсе новостей и отвлекаться будете только один раз в
день.

### Хочу писать в рассылку с любого почтового адреса

Чтобы оградить подписчиков от спама администраторы почтовых рассылок запрещают
писать туда с адресов, не подписанных на рассылку. Поэтому если хочется
участвовать в обсуждениях, то нужно подписаться. Но если у вас несколько
почтовых адресов, то возникает путаница: на какой адрес я подписался и с какого
можно писать?

В Mailman есть возможность добавить дополнительные почтовые адреса, с которых вы
можете писать в рассылку.

### Хочу поднять старую переписку

На закуску моя самая любимая хитрость.
Вы каким-то образом нашли интересное обсуждение в архиве рассылки, но по
каким-то причинам вы то ли не были подписаны на рассылку на тот момент, то ли
уже удалили письма из своего ящика. Вообщем у вас нет писем из этой переписки,
но хотелось в неё включиться. Majordomo позволяет отправить самому себе письмо
из архива.

Как это сделать:

* нужно открыть в браузере веб-интерфейс списка рассылки (например
[lists.openbsd.org](https://lists.openbsd.org/)) и залогиниться в нём
* выбрать список рассылки
* выбрать "Summary of the Availabe Archives"

<img src="/images/ml-1.png" vspace="5" hspace="6">

* выбрать письмо в архиве

<img src="/images/ml-2.png" vspace="5" hspace="6">

* в новой вкладке с открытым письмом пролистать вниз и выбрать "Mail this
message to"

<img src="/images/ml-3.png" vspace="5" hspace="6">

Продуктивных переписок вам.
