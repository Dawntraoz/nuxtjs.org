---
title: Введение
description: 'Nuxt.js — это фреймворк для создания приложений на Vue.js. Вы можете выбрать между Универсальным, Статически-Сгенерированным или Одностраничным приложением.'
category: prologue
position: 1
---

> Nuxt.js — это фреймворк для создания приложений на Vue.js. Вы можете выбрать между Универсальным, Статически-Сгенерированным или Одностраничным приложением.

## Что такое Nuxt.js?

Основной задачей этого фреймворка является **рендеринг пользовательского интерфейса** в условиях абстракции от клиент-серверной архитектуры.

Наша цель — создать фреймворк настолько гибкий, чтобы его можно было использовать и как основу, и как дополнение к уже существующим проектам на Node.js.

Nuxt.js содержит все необходимые конфигурационные заготовки, позволяющие сделать разработку приложений **с серверным рендерингом** на Vue.js более приятной.

В дополнение, мы также предоставляем другую опцию разработки: _nuxt generate_. С помощью неё можно **статически генерировать** приложения на Vue.js. На наш взгляд, эта опция может оказаться следующим большим шагом на пути разработки микросервисных веб-приложений.

Кроме того, вы можете использовать Nuxt.js для быстрого создания одностраничных приложений (`spa` mode). Это будет полезно для сохрания возможностей Nuxt при разработке внутренних интерфейсов.

Как фреймворк, Nuxt.js привносит множество возможностей, помогающих разработке, таких как: Асинхронные данные, Middleware, Шаблоны и др.

## Как это работает

![Vue с Webpack и Babel](https://i.imgur.com/avEUftE.png)

Nuxt.js использует следующие элементы для создания современных веб-приложений:

- [Vue 2](https://vuejs.org/)
- [Vue Router](https://router.vuejs.org/en/)
- [Vuex](https://vuex.vuejs.org/ru/) (только при использовании [опции store](/guide/vuex-store))
- [Vue Server Renderer](https://ssr.vuejs.org/ru/) (только при использовании [`mode: 'spa'`](/api/configuration-mode))
- [Vue-Meta](https://github.com/nuxt/vue-meta)

Общий размер составляет всего лишь **57kb min+gzip** (60kb при использовании Vuex).

Под капотом мы используем [webpack](https://github.com/webpack/webpack) с [vue-loader](https://github.com/vuejs/vue-loader) и [babel-loader](https://github.com/babel/babel-loader) для сборки, разделения и минимизации вашего кода.

## Возможности

- Написание Vue-файлов
- Автоматическое разделение кода
- Серверный рендеринг
- Мощная система маршрутизации с Асинхронными данными
- Обслуживание статических файлов
- Транспиляция [ES2015+](https://babeljs.io/docs/en/learn/)
- Сборка и минификация JS & CSS
- Управление элементами в блоке `<head>` (`<title>`, `<meta>` и др.)
- Горячая замена модулей при разработке
- Пре-процессоры: SASS, LESS, Stylus, и др.
- HTTP/2 push headers ready
- Расширение с модульной архитектурой

## Схема

Это схема показывает, как работает Nuxt.js при вызове сервера или когда пользователь совершает переход по приложению через `<nuxt-link>`:

![nuxt-schema](/nuxt-schema.svg)

## Серверный рендеринг (Universal SSR)

Вы можете использовать Nuxt.js как фреймворк для организации всех этапов рендеринга UI в вашем проекте.

Выполнение команды `nuxt` запускает сервер разработки, поддерживающий горячую замену модулей и [Vue Server Renderer](https://ssr.vuejs.org/ru/) автоматически сконфигурированный серверный рендеринг вашего приложения.

### Одностраничное приложение (SPA)

Если, по какой-либо причине, вы предпочитаете не использовать серверный рендеринг, или вам нужен статический хостинг для ваших приложений, вы можете просто использовать SPA режим используя `nuxt --spa`. В комбинации со свойством _generate_, это даёт вам мощный механизм развёртывания одностраничного приложения без необходимости использовать Node.js в режиме реального времени или другие специальные обработки сервера.

Взгляните на следующие [команды](/guide/commands), чтобы узнать больше.

Если же сервер у вас уже есть, вы можете подключить Nuxt.js используя его в качестве промежуточного слоя. Нет никаких ограничений при использовании Nuxt.js для разработки универсальных веб-приложений. Смотрите руководство [Использования Nuxt.js программно](/api/nuxt).

## Статическая генерация (Pre Rendering)

Большая инновация Nuxt.js приходит с командой `nuxt generate`.

Эта команда генерирует HTML-представление для каждого из ваших маршрутов и сохраняет их в соответствующие файлы.

<div>
  <a href="https://vueschool.io/courses/static-site-generation-with-nuxtjs?friend=nuxt" target="_blank" class="Promote">
    <img src="/static-site-generation-with-nuxtjs.png" alt="Статическая генерация сайта с помощью Nuxt.js от vueschool"/>
    <div class="Promote__Content">
      <h4 class="Promote__Content__Title">Статическая генерация сайта с помощью Nuxt.js</h4>
      <p class="Promote__Content__Description">Узнайте, как сгенерировать статический сайт (пре-рендеринг) для повышения призводительности и SEO при одновременном устранении затрат на хостинг</p>
      <p class="Promote__Content__Signature">Видео курсы созданы VueSchool для поддержки разработки на Nuxt.js.</p>
    </div>
  </a>
</div>

Для примера, посмотрим следующую структуру файлов:

```bash
-| pages/
----| about.vue
----| index.vue
```

Будет сгенерировано, как:

```
-| dist/
----| about/
------| index.html
----| index.html
```

Благодаря этому, вы сможете размещать ваши сгенерированные приложения на любом статическом хостинге!

Лучший пример — этот сайт. Он сгенерирован и размещён на [Netlify](https://www.netlify.com). Смотрите наш [исходный код](https://github.com/nuxt/nuxtjs.org) или [Как развернуть Nuxt.js на Netlify](https://vueschool.io/lessons/how-to-deploy-nuxtjs-to-netlify?friend=nuxt) от Vue School.

Мы не хотим вручную генерировать приложение каждый раз, поэтому мы обновляем [документацию репозитория](https://github.com/nuxt/docs). Это вызывает событие для Netlify, которое:

1. Клонирует [репозиторий nuxtjs.org](https://github.com/nuxt/nuxtjs.org)
2. Устанавливает зависимости с помощью `npm install`
3. Запускает `npm run generate`
4. Размещает директорию `dist`

Таким образом, у нас теперь есть **Статически Сгенерированное Веб Приложение** :)

Неудержимая мысль влечёт нас дальше: представьте интернет-магазин, созданный посредством `nuxt generate` и размещённый на CDN. Каждый раз, когда товар заканчивается на складе, мы регенерируем приложение. Но если во время этого процесса кто-то использует наше приложение — всё будет актуально благодаря запросам к API интернет-магазина. Больше нет нужды во множественных серверах и кешировании!

<div class="Alert">

Смотрите [Как развернуть приложение на Netlify?](/faq/netlify-deployment) для дополнительних сведений о развёртывании на Netlify.

</div>