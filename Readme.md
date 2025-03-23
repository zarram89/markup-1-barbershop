# Личный проект по верстке «Barbershop»

## Записи

### 1.Старт

#### Показать скрытые файлы в mac

Комбинация `Command + Shift + . (точка)`

#### Как сделать скриншот

`Ctrl + C` — скопировать выделенный участок текста, файл, картинку;
`Ctrl + V` — вставить то, что скопировали из буфера обмена, в файл или в папку;
`Ctrl + A` — выделить всё. Это может быть весь текст или все файлы в папке;
`Ctrl + X` — вырезать. Работает как сочетание Ctrl + C, только файл или текст пропадут из того места, откуда его вырезали.

Скриншот можно вставить в readme.md или коммит GitHub. Причем картинка сразу же загружается и вставляется уже в синтаксисе Markdown:

![image] (https://www.google.com/imgres?q=code&imgurl=https%3A%2F%2Fwww.economist.com%2Fcdn-cgi%2Fimage%2Fwidth%3D1424%2Cquality%3D80%2Cformat%3Dauto%2Fsites%2Fdefault%2Ffiles%2Fimages%2F2015%2F09%2Fblogs%2Feconomist-explains%2Fcode2.png&imgrefurl=https%3A%2F%2Fwww.economist.com%2Fthe-economist-explains%2F2015%2F09%2F08%2Fwhat-is-code&docid=w7c9ey78vr5vjM&tbnid=jcQDygbv4FhpuM&vet=12ahUKEwizptmNkYuMAxW4UVUIHR0HLO4QM3oECBgQAA..i&w=1190&h=670&hcb=2&ved=2ahUKEwizptmNkYuMAxW4UVUIHR0HLO4QM3oECBgQAA)

##### Windows 10

Откройте нужное изображение и нажмите кнопку `PrtSc` (или `PrintScreen`). Изображение сохранится в буфер обмена.

Откройте графический редактор. Простейший редактор в Windows — это программа Paint. Нажмите кнопку Вставить или комбинацию клавиш `Ctrl + V`.

В Windows 10 также есть возможность сохранять скриншоты сразу, без буфера обмена и манипуляций с графическим редактором. Для этого нужно нажать сочетание клавиш `Windows + PrtSc`. Скриншот в формате png сохранится в папку Изображения/Снимки экрана. Каждому файлу автоматически присваивается имя с индексом, например: «Снимок экрана (20)», так что найти нужный файл не составит труда.

##### Менеджер буфера обмена

Если вы активно копируете и вставляете тексты, картинки и прочее, особенно это легко делать с помощью сочетаний `Ctrl + C` - `Ctrl + V`, то, возможно, замечали, как хочется вернуться к предыдущему копированию. Такая возможность есть, для этого нужно вызвать системный менеджер буфера обмена с помощью `Windows + V`. В выпадающем списке посмотреть список копирований и выбрать нужное копирование.

##### Linux

Снимок всего экрана в Linux можно сделать точно так же, как в Windows: кнопкой `PrintScreen`.

Снимок части экрана можно сделать с помощью комбинации клавиш `Shift + PrtSc`r. Курсор превратится в крестик, и им можно будет выделить область скриншота.

Все скриншоты автоматически сохранятся в папке «Изображения» в формате png. Найти нужные файлы очень легко: название начинается со слов «Снимок экрана от» и содержит дату и время снимка.

##### macOS

Чтобы в macOS сделать снимок всего экрана целиком, нажмите кнопки `Command + Shift + 3`. Файл со снимком экрана сохранится на рабочий стол.

В macOS очень легко сделать снимок части экрана. Для этого нужно нажать сочетание кнопок `Command + Shift + 4` и выделить курсором часть экрана.

Выбранную область можно передвинуть. Для этого нужно зажать клавишу space и, удерживая её, переместить курсором выделенную область. Если вы хотите отменить создание снимка, то нажмите кнопку Esc.

### 2. Разметка

Мнемоники — это особые строки, которые начинаются с амперсанда (&) и заканчиваются точкой с запятой (;). Например, знак меньше на страницу можно вставить мнемоникой `&lt;` (less than), а знак больше мнемоникой `&gt;` (greater than):

Существует множество других символов-мнемоник. Например: `&copy;`, `&laquo;`, `&raquo;`, `&sect;`.

(Мнемоники)[https://html.spec.whatwg.org/multipage/named-characters.html]
(Спецификация HTML Living Standard)[https://html.spec.whatwg.org/multipage/#toc-dom]

#### Вкладывание тегов

Чтобы определить, можно ли один тег вложить в другой, нужно проанализировать раздел Categories у вкладываемого тега и раздел Content model у тега, в который вкладываем.

Проверим, можно ли вложить `p` в `ul`?

- Для этого смотрим, какая модель содержания (поле Content model) у тега, в который вкладывается другой тег. В нашем случае у тега ul в Content model находится Zero or more li and script-supporting elements.

- Проверяем категории (поле Categories) у тега, который вкладываем в другой тег. В нашем случае у тега p категории Flow и Palpable.

#### Основные правила именования:

- Как можно меньше использовать цифры или любое указание на порядок, если это не требуется.
- Разделители слов — дефисы - и нижние подчёркивания _.
- Общепринятые слова и сокращения.
- Использование строчных букв.
- Не использовать спецсимволы, пробелы, кириллицу.
- Хороший код всегда понятен, даже если сильно не вчитываться, а также его можно прочитать быстро, не испытывая трудностей.

#### 1. Крупные смысловые блоки

Вспомним назначение каждого из указанных семантических тегов:

`<header>` — это вводная часть всего документа или одного из его разделов;
`<main>` — основное содержимое страницы — то, что не повторяется на других страницах, уникальное содержимое каждой страницы;
`<footer>` — это заключительная часть всего сайта или смыслового раздела со справочной информацией.

#### 2. Выделяются крупные смысловые элементы

`<nav>` — главная навигация;
`<section>` — смысловой раздел, который нельзя отделить от конкретной страницы или документа;
`<article>` — отделяемый от сайта смысловой раздел;
`<aside>` — дополнительное содержимое.

#### 3. Выделяются заголовки

`<h1>` - `<h6>` - Используем скрытые заголовки, в секциях где они не обозначены

#### 4. Разметка структурных элементов

- Размечаем списки
- Размечаем таблицы
- Размечаем демонстрационные материалы
- Размечаем параграфы и переносы
- Размечаем формы
- Размечаем цитаты
- Размечаем контактную информацию
- Размечаем прогресс и измерения

Определить, какие теги использовать, можно методом исключения:

- Получилось найти самый подходящий смысловой тег — использовать его.
- Для потоковых контейнеров — <div>.
- Для мелких фразовых элементов (слово или фраза) — <span>.

#### 5. Разметка фразовых элементов

- Размечаем изображения
- Размечаем ссылки
- Размечаем кнопки
- Размечаем видеоконтент
- Размечаем время
- Размечаем мелкие текстовые элементы

Попробуем найти на макетах фразовые элементы:

- `<img>`
- `<a>` и `<button>`
- `<video>`
- `<b>`, `<i>` и их семантических «родственников» `<strong>` и `<em>`
- `<time>`
- `<span>`

Так или иначе, `<video>` — это интерактивный контент, который скорее всего будет управляться скриптом, и который непросто стилизуется. Для семантической вёрстки достаточно разметить ссылки на все три основных формата видео, прописать размеры, определить, что будет загружено сразу при обновлении страницы, задать обложку.

```js
<video controls  poster="img/preview.jpg" preload="metadata" width="400" height="320">
  <source src="video.mp4" type="video/mp4">
  <source src="video.ogv" type="video/ogg">
  <source src="video.webm" type="video/webm">
</video>
```

#### Изображение
Товар или логотип - Реализация: <img>

Вспомогательная иконка, декоративное - Реализация: background-image для псевдоэлемента.

Фоновое изображение, декоративное - Реализация: background-image для всего блока.

Изображение в промослайдере - Реализация: <img> или Реализация: background-image для всего блока в зависимости от того важное это изображение о товаре или просто декоративный фон.

Карта - Реализация: <img> (атрибут alt должен описывать изображение, в данном случае — Карта офиса по адресу улица Строителей, 15)

Иконки соцсетей - Реализация: background-image для ссылки.  Таким образом, здесь применяется комплексный подход: внутри ссылки обязательно прописывается поясняющий текст. Изображение на этих кнопках-ссылках декоративные. Для доступного скрытия текста ссылки необходимо добавить класс .visually-hidden.

### 3. Графика

(SVGO)[https://jakearchibald.github.io/svgomg/]

Для SVG: точность 2.

(Squoosh)[https://squoosh.app/]

- Для MozJPEG: Проверить есть ли в продвинутых настройках (Advanced settings) галочка Progressive rendering (Послойная загрузка и улучшение), Quality ~75%-80%, .
- Для OxiPNG: уровень сжатия 2.

Для того чтобы предотвратить открытие файлов прямо в браузере, у тега `<a>` существует атрибут `download`s, который поможет именно скачать файл.
При скачивании или загрузке файлов со сторонних сайтов для безопасности можно использовать атрибут `rel="noopener"`. Этот атрибут позволяет игнорировать скрипты сторонней страницы, которые могут влиять на загрузку файла. Особенно актуален этот атрибут в случае, если загрузка происходит в новой вкладке или новом окне.

```html
<a href="file.pdf" download>Браузер скачает меня, а не будет читать</a>
```

Когда alt-текст не нужен:
- Когда картинка декоративная и не имеет смысла.
- Аватарка: имя пользователя и так у нас уже есть.
- Превью к статье: у нас уже есть заголовок, и этого будет достаточно.
- Иконки в кнопке.

Если картинка оформительская и не требует alt, то не нужно писать туда пробел или его аналоги.
Лучше оставлять пустой alt, чем удалять. Из двух зол выбирают наименьшее. Поэтому лучше оставлять пустой alt.

### 4. Базовая стилизация

Во-первых, можно подключить их в HTML, в метаданных сайта.
Вот как выглядит подключение стилевого файла со шрифтом:

```html
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <link href="https://fonts.googleapis.com/css2?family=Amatic+SC:wght@400;700&display=swap" rel="stylesheet">

  <link rel="stylesheet" href="css/style.css">
</head>
```

Во-вторых, во вкладке @import можно скопировать код для встраивания в CSS. Это полезно, если шрифт применяется только как декоративный, или если нет доступа в метаданные сайта HTML-файле. Этот метод не рекомендуется, так как замедляет отрисовку сайта в браузере.

```css
@import url("https://fonts.googleapis.com/css?family=Amatic+SC:400,700&display=swap&subset=cyrillic,latin");
```

Подключение локальных шрифтов:

```css
@font-face {
  font-family: "Font";
  src: url("font.woff2") format("woff2"),
       url("font.woff") format("woff");
  font-weight: 400;
  font-style: normal;
}
```

```css
@font-face {
  font-family: "Roboto";
  font-weight: 400;
  font-style: normal;
  src: url("roboto.woff2") format("woff2"),
       url("roboto.woff") format("woff");
}
@font-face {
  font-family: "Roboto Bold"; /* указали насыщенность прямо в семействе */
  font-weight: 700;
  font-style: normal;
  src: url("robotobold.woff2") format("woff2"),
       url("robotobold.woff") format("woff");
}

// Используем шрифты для стилизации:

body {
  font-family: "Roboto", "Arial", sans-serif;
}

.title {
  font-family: "Roboto Bold", "Arial", sans-serif;
  font-weight: 700; /* если не загрузится Roboto, подменный безопасный шрифт Arial не сможет стать жирным, если не указывать это свойство */
}
```

(Transfonter)[https://transfonter.org]
(Безопасные шрифты)[https://www.cssfontstack.com]

Требование к веб-безопасным шрифтам: они должны относиться к тому же семейству, что и «декоративный» шрифт. Для шрифтов с «засечками» — это может быть Times New Roman, Georgia, «без засечек» — Arial, Verdana.

```css
{
  font-family: "Some Beautiful Sans Serif Font", "Arial", sans-serif;
}

{
  font-family: "Some Beautiful Serif Font", "Times New Roman", serif;
}
```

При выгрузке векторной графики важно убедиться, что выгрузились именно векторные формы, описанные точками, а не тег <text>, в который обёрнуты буквы и приписаны стили.

```html
<!-- Пример с векторными формами внутри изображения -->
<svg width="106" height="41" viewBox="0 0 106 41" fill="none" xmlns="http://www.w3.org/2000/svg">
  <path d="M34.7969 20.1797C34.7969 22.0651 34.2734 … 19.7891Z" fill="black"/>
</svg>

<!-- Пример с текстом внутри векторного изображения -->
<svg xmlns="http://www.w3.org/2000/svg">
  <style>
    .dollytext {
      font-family: "Open Sans", sans-serif;
      font-size: 16px;
    }
  </style>
  <text x="10" y="100" class="dollytext">
    DOLLY
  </text>
</svg>


<!-- Раз это картинка, с которой нельзя скопировать текст, и её содержание ускользнёт от ридеров и роботов, стоит написать для неё визуально или скрытый текст, или хороший `alt` -->

<img src="img/some-pic.jpg" alt="Выход из зоны комфорта: то, что нам советуют. Но нельзя выйти оттуда, куда ты ещё не входил">

Или

<p class="visually-hidden">Выход из зоны комфорта: то, что нам советуют. Но нельзя выйти оттуда, куда ты ещё не входил</p>
```

(Полный список встроенных стилей)[https://www.w3schools.com/cssref/css_default_values.php]

#### Правила организации внешних отступов в вёрстке

Браузерные стили могут немного различаться в разных браузерах, и вы наверняка столкнётесь с тем, что они вам мешают. Особенно могут мешать встроенные отступы у текстовых элементов. Списки, параграфы, заголовки и цитаты имеют внешние отступы. По умолчанию установлены размеры для margin-top и margin-bottom. Иногда встроенные отступы нужны, так как препятствуют тому, чтобы текст слипся, и задают ему ритм, но чаще всего их приходится обнулять, чтобы они не мешали в расчётах.

##### Выпадение вертикальных отступов

Мы уже решили, что будем сбрасывать все верхние отступы. Так что наложение отступов сверху родительского блока нас не должно коснуться. Но схлопываются также и нижние отступы. Выход простой: нужно обнулить нижний отступ у последнего дочернего элемента. Это можно сделать, используя псевдокласс `:last-child`.

```css
.item {
  margin-bottom: 20px;
}

.item:last-child {
  margin-bottom: 0;
}
```

Вариант: можно задать отступ всем дочерним элементам, кроме последнего.

```css
.item:not(:last-child) {
  margin-bottom: 20px;
}
```

##### Отступ под изображением

 Дело в том, что по спецификации тег img, как это ни странно, — строчный элемент, и поэтому к нему применяется свойство vertical-align. В браузерах строчные элементы выравниваются по базовой линии (baseline), а пустое пространство — это пространство под выносной элемент букв (например, под нижние хвостики букв р или у).

Избавиться от отступа под изображением очень просто: нужно сменить способ отображения элемента и задать изображению свойство `display: block`.

##### Общие правила

- Сбрасывайте браузерные стили по умолчанию.
- Задавайте текстовым элементам нижний отступ.
- Не забывайте сбрасывать отступ у последнего элемента.
- Изображениям, с помощью класса, изменяйте блочную модель:
```html
<img class="product-image" width="100" heigth="100" alt="Перфоратор Т1000">
```
```css
.product-image {
  display: block;
}
```

#### Наследуемые свойства

К наследуемым относятся в основном свойства, определяющие параметры отображения текста: `font-size`, `font-family`, `font-style`, `font-weight`, `color`, `text-align`, `text-transform`, `text-indent`, `l`ine-height`, `letter-spacing`, `word-spacing`, `white-space`, `direction` и другие. Также к наследуемым свойствам относятся list-style, cursor, visibility, border-collapse и некоторые другие.

#### Ненаследуемые свойства

Основные ненаследуемые свойства — это параметры позиционирования, размеров, отступов, фона, рамок: `background`, `border`, `padding`, `margin`, `width`, `height`, `position` и другие.

Составные свойства

```css
  font: 16px/26px "Arial", sans-serif;
  background: #ffffff url("img/bg-page.png") no-repeat top center;
```
```css
  font-size: 16px;                  /* было задано в font */
  line-height: 26px;                /* было задано в font */
  font-family: "Arial", sans-serif; /* было задано в font */
  font-weight: normal;              /* не было задано в font */
  font-style: normal;               /* не было задано в font */
  font-variant: normal;             /* не было задано в font */
```

#### Селекторы

<b>Соседние селекторы</b> записываются с помощью знака `+`, например, `селектор1 + селектор2`. Стили применятся к элементу, подходящему под селектор2, только если сразу перед ним расположен элемент, подходящий под селектор1.
```html
<ul>
  <li class="hit"></li>
  <li class="miss"></li>
</ul>
```

<b>Дочерние селекторы</b> `ul > li > span`
```html
<ul>
  <li><span>...</span></li>
  <li><span>...</span></li>
</ul>
```

<b>Псевдокласс</b> добавляется к селектору c помощью символа `:`, вот так `селектор:псевдокласс`

```css
a:visited { ... }
li:first-child { ... }
li:last-child { ... }
.alert:hover { ... }

li:nth-child(2) { ... } // выбирать теги по порядковому номеру,
li:nth-child(4) { ... }
li:nth-child(2n) { ... }

a:hover { ... } // этот псевдокласс позволяет выбрать элемент, когда на него наведён курсор мыши и кнопка мыши не нажата
tr:hover { ... }
.menu-item:hover { ... }
```

<b>Динамические эффекты с помощью :hover</b>

Львиная доля динамических эффектов, создаваемых с помощью CSS, опираются на несколько псевдоклассов, главный из которых, конечно же, :hover. Весь секрет заключается в сочетании контекстных селекторов и псевдоклассов. Посмотрите на пример:
```css
li.top ul.submenu {
  display: none;
}

li.top:hover ul.submenu {
  display: block;
}
```
Общий принцип такой: родительский элемент реагирует на наведение мыши и изменяет свойства элементов-потомков. То есть всё работает на контекстных селекторах вида `селектор1:hover селектор2`.

<b>Псевдоклассы :link, :visited и :active</b>

```css
a:link { ... } // выбирает ещё не посещённые ссылки.
a:visited { ... } // выбирает посещённые ссылки
a:hover { ... }
a:active { ... } // выбирает активные ссылки (кнопка мыши зажата на ссылке)
```
Обратите внимание на порядок правил. Если их расположить по-другому, то некоторые могут не сработать.


<b>Псевдокласс `:focus`</b> позволяет выбрать элемент, который в данный момент в фокусе. Например, текстовое поле, в которое установлен курсор, находится в фокусе.

В фокусе могут быть не только текстовые поля. Если вы переключаетесь между элементами веб-страницы с помощью клавиши `tab`, то в фокус будут попадать ссылки.

```css
input:focus {
  /* стили для поля в фокусе */
}
```

<b>Селекторы атрибутов</b> селекторы атрибутов записываются с использованием квадратных скобок: `элемент[атрибут]`

```css
input[checked] { ... }
input[type="text"] { ... }
```

```css
input[required] {
  background-color: #fcf8e3;
}

input[type="password"] {
  background-color: #f2dede;
}
```
Селектор по id
```html
  <p id="greeting">Приветствие!</p>
```
```css
#greeting { ... }
```

#### Шрифты

На самом деле, кроме `serif` и `sans-serif` есть ещё менее распространённые типы шрифта:

`monospace` — моноширинный шрифт;
`cursive` — шрифт с неформальным начертанием, например, имитация рукописного текста или леттеринга;
`fantasy` — декоративный шрифт, например, всемирно известный Comic Sans.

#### Насыщенность шрифта

На самом деле, font-weight может принимать одно из девяти числовых вариантов насыщенности:

100: Thin;
200: Extra Light (Ultra Light);
300: Light;
400: Normal;
500: Medium;
600: Semi Bold (Demi Bold);
700: Bold;
800: Extra Bold (Ultra Bold);
900: Black (Heavy).

Но в большинстве системных шрифтов всё равно есть только два варианта толщины: обычный `normal` (400) и жирный `bold` (700). Поэтому и остальные значения свойства используются реже.

В отличие от `text-align` свойство `vertical-align` задаётся самому элементу, а не содержащему его контейнеру:

#### Закрепление фона

```css
background-attachment: fixed;
```
```css
background: [bc] [bi] [br] [bp] [ba];
/* Обозначения:
[bc] — background-color
[bi] — background-image
[br] — background-repeat
[bp] — background-position
[ba] — background-attachment
*/
```

#### Значения-функции

```css
/* Получает содержимое атрибута */
content: attr(href);

/* Любые расчёты */
width: calc(100% - 100px);

/* Линейный градиент */
background-image:
  linear-gradient(45deg, yellow, green);
```

#### Цветовые значения

```css
color: #f00;       /* #f  0  0 */
color: #ff0000;    /* #ff 00 00 */
color: rgb(255, 0, 0);
color: rgba(255, 0, 0, 0.5);
color: hsl(0, 100%, 50%);
color: hsla(0, 100%, 50%, 0.5);
```

#### Значения в виде произвольных строк

И последний на сегодня тип значений — произвольные строки. Обычно — это названия шрифтов или значение того самого свойства `content`.

```css
font-family: "Times New Roman", serif;
content: "Привет!";
```
Однако, `content` — это свойство, которое работает только у псевдоэлементов. Псевдоэлементы чаще всего используются для создания декоративных эффектов, в которых текстовое содержание не нужно, поэтому для `content` задаётся пустая строка.

#### CSS-директивы

Это специальные конструкции, которые начинаются с символа @. Директивы чаще всего влияют на весь документ, но сами по себе ничего не стилизуют. Например, директива @font-face позволяет подключать на страницу нестандартные шрифты, которые потом можно использовать в свойстве font-family. Или директива @media, которая при определённых условиях активирует или деактивирует какие-то CSS правила. Директиву @font-face вы будете использовать уже на этом уровне. С помощью @media делают адаптивную вёрстку, которую мы детально разбираем на втором уровне.

```css
@font-face {
  font-family: "Open Sans";
  src:
    url("OpenSans-Regular.woff2") format("woff2"),
    url("OpenSans-Regular.woff") format("woff");
}

@media (max-width: 600px) {
  .sidebar {
    display: none;
  }
}
```

#### Подключение шрифтов с помощью @font-face

Базовый вариант правила:

```css
@font-face {
  font-family: "Roboto";
  font-style: normal;
  font-weight: 400;
  /* Браузер сначала попробует найти шрифт локально */
  src: local("Roboto"),
       /* Если не получилось, загрузит woff2 */
       url("/fonts/roboto.woff2") format("woff2"),
       /* Если браузер не поддерживает woff2, загрузит woff */
       url("/fonts/roboto.woff") format("woff");
}

/* Теперь можно использовать шрифт */
body {
  font-family: "Roboto", "Arial", sans-serif;
}
```

Для улучшения производительности правило @font-face лучше всего прописывать в самом начале CSS-файла. Так браузер сможет раньше начать обработку шрифта.

#### Оптимизация
Выбор современного формата шрифта, который обладает хорошей степенью сжатия — это только первый шаг к оптимизации. Можно сделать гораздо больше, чтобы ускорить загрузку страницы и сделать пользовательский опыт при взаимодействии с интерфейсом приятнее.

#### FOIT, FOUT и FOFT
Пока шрифт загружается, при рендеринге можно наблюдать разное поведение текста.

- FOIT (Flash of Invisible Text) — с англ. «мелькание невидимого текста». При таком поведении, пока шрифт не загрузится, текст не отображается и появляется только после загрузки шрифта. Значительная проблема — во время загрузки нет доступа к текстовому контенту.

- FOUT (Flash of Unstyled Text) — с англ. «мелькание неоформленного текста». Во время загрузки используется шрифт, заданный по умолчанию (системный, например), а после загрузки страница перерисовывается с использованием загрузившегося шрифта. Эта перерисовка довольно заметна и может быть нежелательна.

- FOFT (Flash of Faux Text) — с англ. «мелькание синтезированного текста». Это поведение можно наблюдать в промежутке, когда основное начертание уже загрузилось, а дополнительные (жирное, курсивное и так далее) — нет. Браузер имитирует нужное начертание до загрузки настоящей версии. В этом случае страница может перерисовываться несколько раз по мере загрузки начертаний.

В разных браузерах логика рендеринга текста во время загрузки шрифта отличается. Например, Chrome и Firefox в течение трёх секунд не отрисовывают ничего, затем используют веб-безопасный шрифт, а после окончания загрузки текст перерисовывается. IE поступает похоже, но при этом не ждёт три секунды. Подобное поведение в разных браузерах можно унифицировать, используя свойство font‑display.

#### Свойство font-display
У свойства есть несколько значений, которые определяют поведение текста во время загрузки шрифта:

- auto — поведение по умолчанию, зависит от браузера.
- block — текст не отображается в течение короткого периода (3 секунды), затем отрисовывается запасной шрифт, если основной ещё не загрузился. Как только загрузка завершается, текст перерисовывается снова.
- swap — сразу же отрисовывается запасной шрифт, после загрузки шрифта — повторный рендеринг.
- fallback — в течение очень короткого периода (100 миллисекунд) не отображается ничего, затем браузер использует запасной шрифт и ждёт 3 секунды — если шрифт всё ещё не загрузился, остаётся запасной шрифт. Далее не важно, загрузился шрифт или нет, замена не произойдёт. Если шрифт загрузится, то он применится только при обновлении страницы.
- optional — текст не отображается в течение 100 миллисекунд, а затем отрисовывается запасным шрифтом. Даже если шрифт загрузится после этого, замена произойдёт только при обновлении страницы.

Оптимальное значение — swap, его можно использовать в большинстве случаев, оно удобно для пользователей. При подключении шрифта с помощью Google Fonts это значение установлено по умолчанию. Если же есть необходимость избежать мелькания текста (например, для вдумчивого чтения), подойдёт optional.

#### Предзагрузка шрифтов
Ещё один способ оптимизации — предварительная загрузка шрифтов. С её помощью можно изменить обычную приоритизацию загрузки ресурсов, тем самым сказав браузеру, что важно загрузить шрифт в первую очередь.

Для того, чтобы предзагрузка сработала, нужно поместить в `<head>` ссылку на шрифт и задать атрибуту `rel` значение `preload`:

```html
<link rel="preload" href="https://htmlacademy.ru/fonts/roboto.woff2" as="font">
```
Также необходимо добавить тип ресурса, в данном случае — font. Предзагружать можно и другие ресурсы — CSS-файлы, изображения и так далее.

#### Как помочь слепым на вашем сайте

(Веблайнд)[https://weblind.ru/]


### 5. Сетки на флексах

#### Блочная модель

- Первый вариант. Вариант по умолчанию, когда ширина не задаётся, соответствует значению width: auto;. В этом случае блок занимает всю ширину родительского блока. Если у блока есть внутренние отступы или рамки, то его ширина содержания автоматически уменьшается, а общая ширина остаётся равной ширине родителя.

- Второй вариант. Когда ширина блока задана явно, например, width: 100%;. В этом случае ширина содержания блока равна ширине родительского блока. Если блоку добавить внутренние отступы и рамки, то его общая ширина становится больше ширины родителя.

Рассмотрим четыре основных типа боксов:

- блочные, display: block,
- строчные, display: inline,
- блочно-строчные, display: inline-block,
- гибкие или флексовые (флексы), display: flex.

#### Свойство display: inline-block

Иногда возникает необходимость расположить в ряд несколько элементов с заданными размерами. Элементы со строчным боксом для этого не подходят, так как не воспринимают размеры. Элементы с блочным боксом тоже не подходят, так как до и после них существует перенос строки. Конечно, блочные боксы можно приспособить для такой задачи, используя дополнительные свойства (которые будут разбираться далее в части про сетки).

Но более простой способ — использовать элементы с блочно-строчным боксом. В HTML нет элементов с блочно-строчным боксом по умолчанию, но любой элемент можно переключить в такой режим отображения, задав ему свойство `display` со значением `inline-block`.

Особенности элементов с блочно-строчным боксом:

- им можно задавать размеры, рамки и отступы, как и элементам с блочным боксом;
- их ширина по умолчанию зависит от содержания, а не растягивается на всю ширину контейнера;
- они не порождают принудительных переносов строк, поэтому могут располагаться на одной строке, пока помещаются в родительский контейнер;
- элементы в одной строке выравниваются вертикально подобно элементам со строчным боксом.

#### Свойство display: none

Значение none свойства `display` используется очень часто. С его помощью можно скрыть элемент, как будто его и не было. Скрытый элемент не отображается и не занимает места на странице.

Это свойство применяется при создании выпадающих меню, динамических галерей, переключающихся вкладок и много где еще.

Есть ещё одно CSS-свойство, которое используется для сокрытия элементов. Это свойство `visibility` со значением `hidden`. Оно «прячет» элемент — он становится невидимым, но занимает место на странице.

#### Алгоритм раскладки на флексах

##### Этап 1. Определение исходных базовых размеров флекс-элементов

Базовый размер — это размер элемента вдоль главной оси.

Исходный базовый размер — это тот размер, который получается, если к флекс-элементу не применять дополнительные возможности флекс-модели. То есть этот размер зависит от обычных свойств блочной модели (`width`, `height`, `padding`, `border`) и содержания элемента.

Если главная ось направлена горизонтально, то на исходный базовый размер влияют:

-свойство width или, если width не задано, ширина содержания (например, длина самого длинного слова),
- горизонтальные паддинги,
- горизонтальные рамки.

Если главная ось направлена вертикально, то на исходный базовый размер влияют:

-свойство height или, если height не задано, высота содержания (например, количество текстовых строк),
-вертикальные паддинги,
-вертикальные рамки.

##### Этап 2. Применение гибких размеров и перераспределение свободного пространства

2.1. Применение гибких размеров

Свойство `flex-grow`отвечает за гибкость на растяжение, или за «жадность» флекс-элемента. Один элемент мы делаем «жадным», задав ему `flex-grow: 1`, и он съедает это свободное пространство. Если мы обоим элементам зададим `flex-grow: 1`, то они свободное пространство разделят пополам.

Когда применяется `flex-grow`? Он нужен для «резиновости» без необходимости соблюдения точных пропорций колонок. Никогда не используйте `flex-grow`, если вам нужно точно управлять шириной. Например, чтобы каждая колонка была шириной ровно 30% родителя, нужно использовать width: 30% или flex-basis: 30%, но никак не `flex-grow`.

Свойство `flex-shrink` отвечает за гибкость на сжатие. Свойство `flex-shrink` может принимать числовые значения и по умолчанию равно единице. Получается, что все флекс-элементы по умолчанию могут сжиматься, если после определения исходных базовых размеров выяснилось, что места во флекс-контейнере не хватает. Причём ужимается только область содержимого, а маргины, паддинги и рамки не ужимаются.

2.2. Применение автоматических отступов

```css
.flex-container {
  display: flex;
  flex-direction: row;
}

.flex-container div:nth-child(2) {
  margin-top: auto;
  margin-left: auto;
  width: 200px;
}
```

Браузеры всегда переводят для отступов значение auto в значение в пикселях. В нашем примере браузер уже «знает» размеры свободного пространства в пикселях вдоль обеих осей. Вдоль главной оси он уже вычел из ширины контейнера ширины элементов, а вдоль поперечной оси он уже вычел из высоты контейнера высоту флекс-элемента (одна строчка текста плюс вертикальные паддинги). Да, вдоль поперечной оси расчёты проще, так как поперечная ось у каждого элемента своя.

##### Лучшие практики работы с внешними отступами

- Сбрасывайте отступы по умолчанию
- Отступы устанавливаются сверху вниз и слева направо
- Не задавайте отступы, если элемент можно переиспользовать
- Сбрасывайте отступ у последнего элемента в группе
```css
.item {
  margin-right: 20px;
}

.item:last-child {
    margin-right: 0;
}
// или
.item:not(:last-child) {
  margin-right: 20px;
}
```

##### Внешние отступы используются:

- Для создания пространства между элементами.
- Для изменения положения элемента.

##### В работе стоит придерживаться этих правил:

- Сбрасывайте отступы по умолчанию.
- Отступы устанавливаются по направлению потока документа: сверху вниз и слева направо.
- Сбрасывайте отступ у последнего элемента в группе.
- Не задавайте отступы блокам, которые можно переиспользовать.

#### Сортировка элементов на CSS

Интересного эффекта можно достичь, если скомбинировать флексбокс с селектором :checked. Подробно трюк с :checked ~ разбирается в задании части «Селекторы. Тонкости».

Приём заключается в следующем: с помощью селектора по выделению чекбокса можно управлять порядком флекс-элементов, изменяя направление главной оси с помощью flex-direction. Лучше всего эффект работает, когда направление главной оси меняется с «сверху вниз» на «снизу вверх».

При этом флекс-контейнер должен находиться в разметке на одном уровне с чекбоксом.

Таким образом реализуется сортировка на CSS, без использования JavaScript.
```html
<!DOCTYPE html>
<html lang="ru">
  <head>
    <meta charset="utf-8">
    <title>Сортировка элементов на CSS</title>
    <link href="" rel="stylesheet">
    <link href="style.css" rel="stylesheet">
  </head>
  <body class="subtle">
    <label for="sort">Сортировать по вкусу</label>
    <input type="checkbox" id="sort" name="sort" class="input-sort">
    <ol class="sort-list">
      <li><a href="/">Мясо</a></li>
      <li><a href="/">Рыба</a></li>
      <li><a href="/">Сметана</a></li>
      <li><a href="/">Молоко</a></li>
      <li><a href="/">Сыр</a></li>
    </ol>
  </body>
</html>
```
```css
.sort-list {
  display: flex;
  flex-direction: column;
}

.input-sort:checked ~ .sort-list {
  flex-direction: column-reverse;
}
```

или прятать по чекбоксу
```css
.sort-list {
  display: non;
}

.input-sort:checked ~ .sort-list {
  display: block;
}
```
