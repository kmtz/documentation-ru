---
date: 2018-01-01
title: Создание первой сцены
description: Изучаем основы создания сцен в Decentraland
redirect_from:
  - /documentation/create-scene/
categories:
  - getting-started
type: Document
set: getting-started
set_order: 1
tag: introduction
---

В Decentraland сцена представляет собой весь контент на участке земли. Все сцены состоят из [сущностей (entities)]({{ site.baseurl }}{% post_url /development-guide/2018-06-21-entity-interfaces %}), которые в свою очередь представляют собой элементы сцены, организованные в древовидные структуры, аналогично тому, как это выглядит в дереве DOM в веб-разработке.

## Установка CLI

Убедитесь что вы уже установили Decentraland. В Mac OS / Linux, вы можете сделать это с помощью этой команды:

```bash
npm install -g decentraland
```

Смотрите [инструкцию по установке]({{ site.baseurl }}{% post_url /getting-started/2018-01-01-installation-guide %}) где вы найдете всю информацию по установке Decentraland для всех платформ.

## Создание файловой структуры

Используйте интерфейс командной строки (CLI) для автоматического создания шаблона сцены. Для этого запустите команду `dcl init` в пустом каталоге.

Команда `dcl init` создает **проект** Decentraland в текущей директории, содержащий вашу **сцену**. Команда потребует ввести ответы на ряд вопросов о сцене, таких как кто является владельцем и куда именно в Decentraland она будет загружена, затем вам нужно будет выбрать один из представленных шаблонов. В зависимости от того, что вы выберете, CLI создаст соответствующую структура файлов и каталогов с различным содержимым.

Существуют различные шаблоны сцен, на данный момент вы можете использовать следующие:

- **Обычная сцена**: Определена в простом файле TypeScript, которыый отрисовывает отдну модель glTF.
- **Интерактивная сцена**: Описана в файле TypeScript, в котором содержится пример с дверью, которую можно открыть. Лучше всего начать изучение SDK именно с этого шаблона. В этой сцене описывается основное состояние объекта и обрабатываются события нажатия на объект. Состояние сцены хранится локально, в браузере пользователя, так что действия пользователя отрисовываются только локально и не влияют на то, что увидят другие пользователи.
- **Удаленная (remote) сцена**: Описана в файле TypeScript таким-же образом, как и интерактивная схема, с той разницей, что состояние хранится на удаленном сервере, связь с которым осуществляется через WebSockets. Поэтому все пользователи видят одно и то-же. Чтобы протестировать свою сцену вы можете запустить ее как через сервер, так и в локальном окружении.
- **Статичная сцена**: Определена в файле **XML** с одной моделью glTF. Вы не можете добавить никакой динамический или интерактивный контент в статичную сцену, она может использоваться только для отрисовки статичного содержимого.

Смотри [содержимое сцены]({{ site.baseurl }}{% post_url /development-guide/2018-01-11-scene-files %}) для обзора основных файлов, которые создаются для сцены.

## Предпросмотр сцены

Для просмотра локальной сцены запустите эту команду в директории проекта:

```bash
dcl start
```

Каждый раз когда вы вносите изменения в вашу сцену, предпросмотр автоматически загружает изменения, так, чтобы не было нужны заново запускать команду.

Чтобы получить больше информации о предпросмотре сцены и о том, как запустить предпросмотр удаленной сцены смотрите раздел [предпросмотр сцены]({{ site.baseurl }}{% post_url /getting-started/2018-01-04-preview-scene %}).

## Редактирование сцены

Для редактирования сцены мы рекомендуем использовать редактор кода, например [Visual Studio Code](https://code.visualstudio.com/) или [Atom](https://atom.io/). Такой редактор поможет вам в создании сцен значительно быстрее и с меньшим количеством ошибок, так как современные редакторы подсвечивают синтаксические ошибки, умеют автоматически дополнять код и даже показывают вам умные подсказки в зависимости от контекста. С помощью With Visual Studio Code вы можете даже кликнуть на объект и получить полное описание его класса.

- В _обычной_ and _интерактивных_ сценах, вы создаете логику вашей сцены в файле _Scene.tsx_.
- В _удаленных_ сценах, вся логика сцены находится в файлах _RemoteScene.tsx_ и _State.tsx_.
- В _статичных_ сценах, весь контент находится в файле _scene.xml_.

Смотрите [руководство по разработке]({{ site.baseurl }}{% post_url /development-guide/2018-01-21-scene-content %}) с иснтрукциями о том, как добавить контент в вашу сцену.

## Публикация сцены

Как только вы закончили создание вашей сцены и хотите загрузить ее на ваш участок, вы можете [опубликовать ее]({{ site.baseurl }}{% post_url /getting-started/2018-01-07-publishing %}).
