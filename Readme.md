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
