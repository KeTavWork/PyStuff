# TITLE

|[Markdown](#markdown-id)|[Git](#git-id)|
|:----------------------:|:------------:|
|[Paragraphs and line breaks](#markdown-plb-id)|[Навигация](#git-nav-id)|
|[Emphasis](#markdown-emph-id)|[Работа с файлами и папками](#git-file-id)|
|[Headings](#markdown-head-id)|[Полезные возможности](#git-trck-id)|
|[Horizontal rules](#markdown-hor-id)|[Репозиторий](#git-repo-id)|
|[Blockquotes](#markdown-quot-id)|[Подготовить файлы к сохранению](#git-add-id)|
|[Lists](#markdown-lst-id)|[Коммит](#git-comm-id)|
|[Links](#markdown-link-id)|[Просмотреть историю коммитов](#git-log-id)|
|[Images](#markdown-img-id)|[SSH](#git-ssh-id)|
|[Code](#markdown-code-id)|[Локальный и удалённый репозитории](#git-remo-id)|
|[Tables](#markdown-tbl-id)|[Хеш](#git-hash-id)|
|[Escaping characters](#markdown-esc-id)|[HEAD](#git-head-id)|
|[Spoilers](#markdown-splr-id)|[Сообщения к коммитам](#git-msg-id)|
|[Mermaid](#markdown-mrmd-id)|[Статусы файлов в Git](#git-stat-id)|

|[Browser](#browser-id)|[Python](#python-id)|
|:--------------------:|:------------------:|

<h1 id="markdown-id">Шпаргалка markdown</h1>

[Шпаргалка по Markdown][GitHubMCSRef] | [Markdown Cheat Sheet][MCSRef]

<h2 id="markdown-plb-id">Параграфы и разрывы строк (paragraphs and line breaks)</h2>

Чтобы поделить текст на параграфы, между ними нужно оставить пустую строку. Строка считается пустой, даже если в ней есть пробелы и табуляции. Если же строки находятся рядом, то они автоматически склеиваются в одну.\
Для переноса строки внутри одного параграфа есть три метода:
1. Поставить в конце строки два или больше пробела `  `.
2. Поставить в конце строки обратную косую черту `\`.
3. Использовать HTML-тег `<br>`.

<details>
<summary>Spoiler</summary>

```md
Перенос с помощью пробелов  
Перенос с помощью обратного слеша\
Перенос с помощью тега <br> Последняя строка
```
Перенос с помощью пробелов  
Перенос с помощью обратного слеша\
Перенос с помощью тега <br> Последняя строка

</details>

<h2 id="markdown-emph-id">Выделение текста (emphasis)</h2>

### *Курсив (italic)* - `*` | `_`

<details>
<summary>Spoiler</summary>

```md
*Текст курсивом*

_Текст курсивом_
```
*Текст курсивом*

_Текст курсивом_

</details>

### **Жирный (bold)** - `**` | `__`

<details>
<summary>Spoiler</summary>

```md
**Жирный текст**

__Жирный текст__
```
**Жирный текст**

__Жирный текст__

</details>

### ***Жирный курсив (bold and italic)***  - `***` | `___`

<details>
<summary>Spoiler</summary>

```md
***Текст жирным курсивом***

___Текст жирным курсивом___
```
***Текст жирным курсивом***

___Текст жирным курсивом___

</details>

**Выделение фрагмена внутри слова корректно сработает только при использовании `*`.**

<details>
<summary>Spoiler</summary>

```md
Кор*рек*тно, кор**рек**тно, кор***рек***тно

Некор_рек_тно, некор__рек__тно, некор___рек___тно
```
Кор*рек*тно, кор**рек**тно, кор***рек***тно

Некор_рек_тно, некор__рек__тно, некор___рек___тно

</details>

### ~Зачёркнутый (strikethrough)~ - `~~`

Такая опция есть только в диалекте GitHub Flavored Markdown.

<details>
<summary>Spoiler</summary>

```md
~~Зачёркнутый текст~~
```
~~Зачёркнутый текст~~

</details>

<h2 id="markdown-head-id">Заголовки (headings)</h2>

Заголовки можно создавать с помощью символа `#`. Чем больше `#`, тем меньше заголовок: от H1 до H6.

<details>
<summary>Spoiler</summary>

```md
# Заголовок первого уровня
## Заголовок второго уровня ##
### Заголовок третьего уровня
#### Заголовок четвёртого уровня #
##### Заголовок пятого уровня ############
###### Заголовок шестого уровня
```
# Заголовок первого уровня
## Заголовок второго уровня ##
### Заголовок третьего уровня
#### Заголовок четвёртого уровня #
##### Заголовок пятого уровня ############
###### Заголовок шестого уровня

</details>

У заголовков первого и второго уровня есть альтернативный способ выделения: на следующей строке после них нужно поставить `=` или `-`. Вот несколько правил:
- `=` применяется для заголовков H1;
- `-` применяется для заголовков H2;
- если в одной строке поставить оба знака, то работать ничего не будет;
- можно ставить любое количество знаков, и на тип заголовка это не повлияет;
- между заголовком и знаками не должно быть пустых строк.

<details>
<summary>Spoiler</summary>

```md
Заголовок первого уровня
=
Заголовок первого уровня
=========
Заголовок второго уровня
-
Заголовок второго уровня
----------
```
Заголовок первого уровня
=
Заголовок первого уровня
=========
Заголовок второго уровня
-
Заголовок второго уровня
----------

</details>

### Heading IDs

Many Markdown processors support custom IDs for headings — some Markdown processors automatically add them. Adding custom IDs allows you to link directly to headings and modify them with CSS. To add a custom heading ID, enclose the custom ID in curly braces on the same line as the heading.\
***WORK ONLY HTML, IDK***

<details>
<summary>Spoiler</summary>

Markdown:
```md
### My Great Heading {#custom-id}
```
HTML:
```html
<h3 id="custom-id">My Great Heading</h3>

<a name="headers"><h2>Заголовки</h2></a>
```

</details>

<h2 id="markdown-hor-id">Разделители (horizontal rules)</h2>

Чтобы оформить горизонтальный разделитель, нужно поставить три или больше специальных символа: `*`, `-` или `_`. Они должны находиться на отдельной строке, и между ними можно ставить любое количество пробелов и табуляций.

<details>
<summary>Spoiler</summary>

```md
***
---
___
*    	*  **
__________________________
```
***
---
___
*    	*  **
__________________________

</details>

<h2 id="markdown-quot-id">Цитаты (blockquotes)</h2>

Чтобы параграф отобразился как цитата, нужно поставить перед ним `>`.

<details>
<summary>Spoiler</summary>

```md
> Оформление цитатой
последовательных строк
внутри одного параграфа
```
> Оформление цитатой
последовательных строк
внутри одного параграфа

</details>

Внутрь одного блока цитаты можно поместить сразу несколько параграфов и использовать любые элементы оформления. Например, заголовки и другие цитаты. Чтобы сделать это, нужно поместить `>` перед началом каждой строки.

<details>
<summary>Spoiler</summary>

```md
> # Заголовок
> Первый параграф
>
> Второй параграф
>
> > Вложенная цитата
> > > Цитата третьего уровня
>
> Продолжение основной цитаты
```
> # Заголовок
> Первый параграф
>
> Второй параграф
>
> > Вложенная цитата
> > > Цитата третьего уровня
>
> Продолжение основной цитаты

</details>

<h2 id="markdown-lst-id">Списки (lists)</h2>

### Нумерованные (ordered)

Для создания нумерованного списка перед пунктами нужно поставить число с точкой. При этом нумерация в разметке ленивая. Неважно, какие именно числа вы напишете: Markdown пронумерует список автоматически.\
Список можно начинать и не с единицы. Для нумерации важно только число, которое стоит перед первым пунктом.\
Между двумя нумерованными списками, идущими подряд, нужно отбить две пустые строки. Если отбить только одну, то Markdown воспримет два списка как один. Некоторые редакторы в таком случае увеличивают интервал между пунктами.

<details>
<summary>Spoiler</summary>

```md
11. Первый пункт
22. Второй пункт
33. Третий пункт

11. Четвёртый пункт
22. Пятый пункт
33. Шестой пункт
```
11. Первый пункт
22. Второй пункт
33. Третий пункт

11. Четвёртый пункт
22. Пятый пункт
33. Шестой пункт

</details>

### Ненумерованные (unordered)

Для создания ненумерованного списка нужно поставить перед каждым пунктом `*`, `-` или `+`.\
Markdown относит к разным спискам пункты, перед которыми стоят разные маркеры. Даже несмотря на отсутствие пустых строк между списками.\
Если же два списка идут подряд, а перед их пунктами стоят одинаковые маркеры, тогда между ними нужно отбить две пустые строки (как в случае с нумерованными списками).

<details>
<summary>Spoiler</summary>

```md
* Первый пункт
* Второй пункт
* Третий пункт
- Первый пункт
- Второй пункт
- Третий пункт
+ Первый пункт
+ Второй пункт
+ Третий пункт
```
* Первый пункт
* Второй пункт
* Третий пункт
- Первый пункт
- Второй пункт
- Третий пункт
+ Первый пункт
+ Второй пункт
+ Третий пункт

</details>

### Чекбоксы (checkboxes)

Чтобы сделать чекбоксы, нужно использовать маркированный список, но между маркером и текстом поставить `[x]` для отмеченного пункта и `[ ]` — для неотмеченного.\
Чекбоксы доступны в диалекте GitHub Flavored Markdown и поддерживаются не всеми редакторами Markdown.

<details>
<summary>Spoiler</summary>

```md
- [x] Отмеченный пункт
- [ ] Неотмеченный пункт
```
- [x] Отмеченный пункт
- [ ] Неотмеченный пункт

</details>

### Вложенные (nested)

Чтобы создать вложенный список, нужно поставить перед его пунктами табуляцию или несколько пробелов. В Markdown одна табуляция соответствует четырём пробелам.\
Список одного вида можно вкладывать в любой другой.

<details>
<summary>Spoiler</summary>

```md
1. Пункт
	1. Подпункт
		1. Подподпункт

- Пункт
	- Подпункт
		- Подподпункт


1. Пункт
	- Подпункт
		* Подподпункт

+ Пункт
	1. Подпункт

- Пункт
  - [x] Отмеченный подпункт
  - [ ] Неотмеченный подпункт
    1. Подподпункт
```
1. Пункт
	1. Подпункт
		1. Подподпункт

- Пункт
	- Подпункт
		- Подподпункт


1. Пункт
	- Подпункт
		* Подподпункт

+ Пункт
	1. Подпункт

- Пункт
  - [x] Отмеченный подпункт
  - [ ] Неотмеченный подпункт
    1. Подподпункт

</details>

На самом деле количество пробелов, которые нужно поставить для корректного отступа, рассчитывается чуть сложнее. Берётся количество символов в маркере (один для `*`, `-` и `+`, два для `1.`, три для `10.`), и к нему прибавляется любое число от 1 до 4.\
Таким образом, если в маркере 1 символ, нужно поставить от 2 до 5 пробелов, если 2 символа — от 3 до 6, если 3 символа — от 4 до 7.

### Другие элементы внутри списков

В пункты списков можно добавлять другие элементы оформления. Например, параграфы или цитаты. Для этого нужно сделать отступ, как если бы вы добавляли вложенный список.

<details>
<summary>Spoiler</summary>

```md
1. Первый пункт
	> Цитата внутри первого пункта
1. Второй пункт
 	
    Параграф внутри второго пункта
1. Третий пункт
```
1. Первый пункт
	> Цитата внутри первого пункта
1. Второй пункт
 	
    Параграф внутри второго пункта
1. Третий пункт

</details>

<h2 id="markdown-link-id">Ссылки (links)</h2>

Самый лёгкий способ поместить ссылку в Markdown — заключить её в `<>`. Несмотря на простоту, он не является основным и был добавлен только в спецификации CommonMark.

Чтобы оформить ссылкой часть текста, используется такой синтаксис: `[текст](ссылка)`. Можно сделать всплывающую подсказку при наведении курсора. Для этого в круглых скобках после ссылки нужно поставить пробел и написать текст подсказки в кавычках.

Ещё один способ оформить ссылку — справочный. Он работает как сноски в книгах: `[текст][имя сноски]`. При таком способе организации ссылок в конце документа нужно также написать и оформить саму сноску: `[имя сноски]: ссылка`. При желании после ссылки можно добавить подсказку — точно так же, как в предыдущем методе.\
Имя сноски может быть любым сочетанием символов: цифрами, буквами и даже знаками препинания. На одну и ту же сноску в тексте можно ссылаться сколько угодно раз.\
Ссылки, оформленные справочным методом, выглядят и работают точно так же, как и в предыдущем способе. Сами сноски в отформатированном документе не отображаются.

<details>
<summary>Spoiler</summary>

```md
<https://skillbox.ru/media/code/>


[Skillbox Media](https://skillbox.ru/media/) без подсказки

[Skillbox Media](https://skillbox.ru/media/ "Всплывающая подсказка") с подсказкой


[Skillbox Media][1]

[Раздел «Код»][code]


[1]: https://skillbox.ru/media "Всплывающая подсказка"
[code]: https://skillbox.ru/media/code/
```
<https://skillbox.ru/media/code/>


[Skillbox Media](https://skillbox.ru/media/) без подсказки

[Skillbox Media](https://skillbox.ru/media/ "Всплывающая подсказка") с подсказкой


[Skillbox Media][1]

[Раздел «Код»][code]


[1]: https://skillbox.ru/media "Всплывающая подсказка"
[code]: https://skillbox.ru/media/code/

</details>

### Linking to Heading IDs

You can link to headings with custom IDs in the file by creating a standard link with a number sign (#) followed by the custom heading ID. These are commonly referred to as anchor links.

<details>
<summary>Spoiler</summary>

Markdown:
```md
[Heading IDs](#heading-ids)
```
HTML:
```html
<a href="#heading-ids">Heading IDs</a>
```

</details>

<h2 id="markdown-img-id">Картинки (images)</h2>

Изображения в Markdown оформляются по принципу, схожему с принципом оформления ссылкок, только перед квадратными скобками нужно поставить восклицательный знак: `![текст](путь к изображению)`. Здесь также можно сделать всплывающую подсказку.

Можно использовать и справочный метод: `![текст][имя сноски]`. Сноски оформляются так же, как и в ссылках: `[имя сноски]: путь к изображению`, — в них тоже можно добавлять подсказки.

<details>
<summary>Spoiler</summary>

```md
![Изображение](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/1920px-Markdown-mark.svg.png "Логотип Markdown")


![Изображение][1]


[1]: https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/1920px-Markdown-mark.svg.png "Логотип Markdown"
```
![Изображение](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/1920px-Markdown-mark.svg.png "Логотип Markdown")


![Изображение][1]


[1]: https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/1920px-Markdown-mark.svg.png "Логотип Markdown"

</details>

<h2 id="markdown-code-id">Вставка кода (code)</h2>

В Markdown есть несколько способов выделить исходный код:
1. Если надо отобразить фрагмент кода внутри строки с каким-то текстом, нужно с двух сторон выделить этот код одним или несколькими обратными апострофами (``` ` ```; их ещё называют бэктиками).
2. Чтобы выделить фрагмент из нескольких строк, нужно с двух сторон выделить его тремя обратными апострофами.
3. Также перед фрагментом кода можно поставить табуляцию или четыре пробела, при этом предыдущая строка должна быть пустой.

<details>
<summary>Spoiler</summary>

```md
Функция `print (x)` выводит содержимое переменной ```x```.

\```
#include <stdio.h>
int main() {
   printf("Hello, World!");
   return 0;
}
\```

	let x = 12;
	let y = 6;
	console.log(x + y);
```
Функция `print (x)` выводит содержимое переменной ```x```.

```
#include <stdio.h>
int main() {
   printf("Hello, World!");
   return 0;
}
```

	let x = 12;
	let y = 6;
	console.log(x + y);

HTML:
```html
<code>`</code>
```
<code>`</code>

</details>

Если обрамлять код тремя обратными апострофами, то после первой тройки можно указать язык программирования — тогда Markdown правильно подсветит элементы кода.

<details>
<summary>Spoiler</summary>

```md
```python
if x > 0:
	print (x)
else:
	print ('Hello, World!')
\```

```c
#include <stdio.h>
int main() {
   printf("Hello, World!");
   return 0;
}
\```

```javascript
let x = 12;
let y = 6;
console.log(x + y);
\```
```
```python
if x > 0:
	print (x)
else:
	print ('Hello, World!')
```

```c
#include <stdio.h>
int main() {
   printf("Hello, World!");
   return 0;
}
```

```javascript
let x = 12;
let y = 6;
console.log(x + y);
```

</details>

Возможность вставлять блоки кода тремя обратными апострофами появилась в спецификации CommonMark, но там не указан список псевдонимов: как правильно называть языки, чтобы Markdown понял, о чём речь. Поэтому каждая реализация ведёт свой собственный список языков и их псевдонимов. Так как их очень много, да ещё и новые время от времени добавляются, то удобных таблиц обычно не делают. Предлагают сразу ознакомиться с конфигурационным файлом.

[Список языков, поддерживаех диалектом GitHub Flavored Markdown][linguistRef]

<h2 id="markdown-tbl-id">Таблицы (tables)</h2>

В диалекте GitHub Flavored Markdown есть возможность оформлять таблицы. Столбцы разделяются `|`, а строка с шапкой отделяется от остальных `-`, которых можно ставить сколько угодно.

<details>
<summary>Spoiler</summary>

```md
|Столбец 1|Столбец 2|Столбец 3|
|-|--------|---|
|Длинная запись в первом столбце|Запись в столбце 2|Запись в столбце 3|
|Кртк зпс| |Слева нет записи|
```
|Столбец 1|Столбец 2|Столбец 3|
|-|--------|---|
|Длинная запись в первом столбце|Запись в столбце 2|Запись в столбце 3|
|Кртк зпс| |Слева нет записи|

</details>

Чтобы выровнять весь столбец по правому краю, в строке с дефисами сразу после дефисов можно поставить `:`. Чтобы выровнять содержимое по центру, надо поставить `:` с обеих сторон.

<details>
<summary>Spoiler</summary>

```md
|Столбец 1|Столбец 2|Столбец 3|
|:-|:-:|-:|
|Равнение по левому краю|Равнение по центру|Равнение по правому краю|
|Запись|Запись|Запись|
```
|Столбец 1|Столбец 2|Столбец 3|
|:-|:-:|-:|
|Равнение по левому краю|Равнение по центру|Равнение по правому краю|
|Запись|Запись|Запись|

</details>

Creating tables with hyphens and pipes can be tedious. To speed up the process, try using the [Markdown Tables Generator][MTGRef] or [AnyWayData Markdown Export][AWDMEFer]. Build a table using the graphical interface, and then copy the generated Markdown-formatted text into your file.

<h2 id="markdown-esc-id">Экранирование (escaping characters) - <code>\</code></h2>

**Список символов, которые нужно экранировать: \[`\`, ``` ` ```, `*`, `_`, `{`, `}`, `[`, `]`, `<`, `>`, `(`, `)`, `#`, `+`, `-`, `.`, `!`, ` `, `|`\]**

<h2 id="markdown-splr-id">Spoilers</h2>

<details>
<summary>Spoiler</summary>
  
```html
<details>
<summary>Spoiler</summary>

  <!-- Markdown content here -->

</details>
```

  <details>
    <summary>Spoiler</summary>
  
    <!-- Markdown content here -->
  
  </details>

</details>

<h2 id="markdown-mrmd-id">Mermaid</h2>

Чтобы получить `mermaid`-схему в `README.md`, нужно добавить блок кода типа `mermaid`. Два символа `%%` обозначают в `mermaid` строку-комментарий.

***[Mermaid website][mermaidRef]***

### Flowcharts

<details>
<summary><h4>A node with text</h4></summary>

```md
```mermaid
---
title: Node with text
---
flowchart LR
    id1[This is the text in the box]
\```
```

```mermaid
---
title: Node with text
---
flowchart LR
    id1[This is the text in the box]
```

</details>


<details>
<summary><h4>Direction</h4></summary>

Possible FlowChart orientations are:
- TB - Top to bottom
- TD - Top-down/ same as top to bottom
- BT - Bottom to top
- RL - Right to left
- LR - Left to right

```md
```mermaid
flowchart TD
    Start --> Stop
\```
```

```mermaid
flowchart TD
    Start --> Stop
```

</details>

<details>
<summary><h4>A link with arrow head and text</h4></summary>

```md
```mermaid
flowchart LR
    A-->|text|B
\```
```

```mermaid
flowchart LR
    A-->|text|B
```

</details>

<details>
<summary><h4>Example</h4></summary>

```md
```mermaid
flowchart LR
    untr[untracked]
    st[staged]
    cm[comitted]
    untr-->|git add|st
    st-->|???|cm
\```
```

```mermaid
flowchart LR
    untr[untracked]
    st[staged]
    cm[comitted]
    untr-->|git add|st
    st-->|???|cm
```

</details>

### Gitgraph Diagrams

<details>
<summary><h4>Basic</h4></summary>

In Mermaid, we support the basic git operations like:
- _commit_ : Representing a new commit on the current branch.
- _branch_ : To create & switch to a new branch, setting it as the current branch.
- _checkout_ : To checking out an existing branch and setting it as the current branch.
- _merge_ : To merge an existing branch onto the current branch.

```md
```mermaid
---
title: Example Git diagram
---
gitGraph
   commit
   commit
   branch develop
   checkout develop
   commit
   commit
   checkout main
   merge develop
   commit
   commit
\```
```

```mermaid
---
title: Example Git diagram
---
gitGraph
   commit
   commit
   branch develop
   checkout develop
   commit
   commit
   checkout main
   merge develop
   commit
   commit
```

</details>

<details>
<summary><h4>Customizing main branch name</h4></summary>

You can do this by using the `mainBranchName` keyword. By default its value is `main`. You can set it to any string using directives.

```md
```mermaid
%%{init: { 'logLevel': 'debug', 'theme': 'base', 'gitGraph': {'showBranches': true, 'showCommitLabel':true,'mainBranchName': 'untracked'}} }%%
    gitGraph
\```
```

```mermaid
%%{init: { 'logLevel': 'debug', 'theme': 'base', 'gitGraph': {'showBranches': true, 'showCommitLabel':true,'mainBranchName': 'untracked'}} }%%
    gitGraph
```

</details>

<details>
<summary><h4>Themes</h4></summary>

The following are the different pre-defined theme options:
- `base`
- `forest`
- `dark`
- `default`
- `neutral`

```md
```mermaid
%%{init: { 'logLevel': 'debug', 'theme': 'dark' } }%%
      gitGraph
\```
```

```mermaid
%%{init: { 'logLevel': 'debug', 'theme': 'dark' } }%%
      gitGraph
```

</details>

<details>
<summary><h4>Adding custom commit id</h4></summary>

For a given commit you may specify a custom ID at the time of declaring it using the `id` attribute, followed by `:` and your custom value within a `""` quote. For example: `commit id: "your_custom_id"`

```md
```mermaid
gitGraph
       commit id: "Alpha"
       commit id: "Beta"
       commit id: "Gamma"
\```
```

```mermaid
gitGraph
       commit id: "Alpha"
       commit id: "Beta"
       commit id: "Gamma"
```

</details>

<details>
<summary><h4>Modifying commit type</h4></summary>

In Mermaid, a commit can be of three type, which render a bit different in the diagram. These types are:
- `NORMAL` : Default commit type. Represented by a solid circle in the diagram
- `REVERSE` : To emphasize a commit as a reverse commit. Represented by a crossed solid circle in the diagram.
- `HIGHLIGHT` : To highlight a particular commit in the diagram. Represented by a filled rectangle in the diagram.

For a given commit you may specify its type at the time of declaring it using the `type` attribute, followed by `:` and the required type option discussed above. For example: `commit type: HIGHLIGHT`\
NOTE: If no commit type is specified, `NORMAL` is picked as default.

```md
```mermaid
gitGraph
       commit id: "Normal"
       commit
       commit id: "Reverse" type: REVERSE
       commit
       commit id: "Highlight" type: HIGHLIGHT
       commit
\```
```

```mermaid
gitGraph
       commit id: "Normal"
       commit
       commit id: "Reverse" type: REVERSE
       commit
       commit id: "Highlight" type: HIGHLIGHT
       commit
```

</details>

<details>
<summary><h4>Adding Tags</h4></summary>

For a given commit you may decorate it as a **tag**, similar to the concept of tags or release version in git world. You can attach a custom tag at the time of declaring a commit using the `tag` attribute, followed by `:` and your custom value within `""` quote. For example: `commit tag: "your_custom_tag"`

```md
```mermaid
gitGraph
       commit
       commit id: "Normal" tag: "v1.0.0"
       commit
       commit id: "Reverse" type: REVERSE tag: "RC_1"
       commit
       commit id: "Highlight" type: HIGHLIGHT tag: "8.8.4"
       commit
\```
```

```mermaid
gitGraph
       commit
       commit id: "Normal" tag: "v1.0.0"
       commit
       commit id: "Reverse" type: REVERSE tag: "RC_1"
       commit
       commit id: "Highlight" type: HIGHLIGHT tag: "8.8.4"
       commit
```

</details>

<details>
<summary><h3>Mermaid pipeline</h3></summary>

```mermaid
sequenceDiagram
    participant dotcom
    participant iframe
    participant viewscreen
    dotcom->>iframe: loads html w/ iframe url
    iframe->>viewscreen: request template
    viewscreen->>iframe: html & javascript
    iframe->>dotcom: iframe ready
    dotcom->>iframe: set mermaid data on iframe
    iframe->>iframe: render mermaid
```

</details>

___
*Это лишь некоторые функции markdown.*

___
<h1 id="browser-id">Browser shortcuts (Cent)</h1>

|Action|Shortcut|
|:-----|:------:|
|Новая вкладка|`Ctrl`+`T`|
|Новая автономная вкладка справа|`Ctrl`+`M`|
|На вкладку слева|`Ctrl`+`Shift`+`Tab`|
|На вкладку справа|`Ctrl`+`Tab`|
|Закрыть текущую вкладку|`Ctrl`+`W`|
|Открыть закрытую вкладку|`Ctrl`+`Shift`+`T`|
|Дублировать вкладку|`Alt`+`U`|
|Закрепить/Открепить текущую вкладку|`Alt`+`N`|
|Вкл. звук/Отк. звук в текущей вкладке|`Alt`+`M`|
|На первую вкладку|`Ctrl`+`1`|
|На последнюю вкладку|`Ctrl`+`9`|
|Последняя посещённая вкладка|`Alt`+`Z`|
|Перейти на предыдущую страницу|`Alt`+`Up`|
|Перейти на следующую страницу|`Alt`+`Down`|
|Установить фокус на первом текстовом поле|`Ctrl`+`Shift`+`U`|
|Назад|`Alt`+`Left`|
|Вперед|`Alt`+`Right`|
|Перезагрузить|`F5`|
|Жесткая перезагрузка|`Ctrl`+`F5`|
|Обновить все вкладки|`Ctrl`+`Shift`+`F5`|
|Очистить историю|`Ctrl`+`Shift`+`Delete`|
|Копировать URL текущей вкладки в буфер обмена|`Alt`+`C`|
|Копировать заголовок и адрес|`Alt`+`L`|
|Открыть URL из буфера обмена|`Alt`+`T`|
|Открыть текущий адрес в мультилогинной вкладке|`Alt`+`Shift`+`O`|
|Переключить просмотр курсора|`F7`|
|Увеличить|`Ctrl`+`+`|
|Уменьшить|`Ctrl`+`-`|
|Сброс масштаба|`Ctrl`+`0`|
|Перейти к адресной строке|`Alt`+`D`|
|Перейти на главную страницу сайта|`Alt`+`O`|
|В закладки текущую страницу|`Ctrl`+`D`|
|Показать меню закладок|`Alt`+`B`|
|Показать/скрыть панель закладок|`Ctrl`+`Shift`+`B`|
|Показать меню списка вкладок|`Alt`+`X`|
|Открыть страницу в IE|`Ctrl`+`Shift`+`E`|
|Отправить ссылку на страницу по электронной почте|`Alt`+`Shift`+`E`|
|Сохранить страницу как…|`Ctrl`+`S`|
|Сохранить страницу как изображение|`Alt`+`I`|
|Сделать снимок всей страницы|`Alt`+`Shift`+`I`|
|Создать ярлык…|`Alt`+`Shift`+`S`|
|Включить/Отключить поверх всех|`Ctrl`+`Shift`+`Y`|
|Отключить/включить звук в текущем процессе|`Alt`+`Shift`+`M`|
|Закрыть браузер|`Ctrl`+`Shift`+`W`|
|Выйти из браузера|`Ctrl`+`Shift`+`Q`|
|Полноэкранный режим|`F11`|
|Настройки|`Alt`+`S`|
|Диспетчер закладок|`Ctrl`+`Shift`+`O`|
|Загрузки|`Ctrl`+`J`|
|История|`Ctrl`+`H`|
|Главная страница|`Alt`+`Home`|
|Перевести эту страницу|`Alt`+`Shift`+`T`|
|Проверить элементы|`Ctrl`+`Shift`+`C`|
|Диспетчер задач|`Shift`+`Escape`|
|Справочный центр|`F1`|

___
<h1 id="git-id">Шпаргалка Git</h1>

<h2 id="git-nav-id">Навигация</h2>

- `pwd` (от англ. *print working directory*, «показать рабочую папку») — покажи, в какой я папке;
- `ls` (от англ. *list directory contents*, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;
- `ls -a` — покажи также скрытые файлы и папки, названия которых начинаются с символа `.`;
- `ls -l` — выдавать (в одноколоночном формате) тип файла, права доступа к файлу, количество ссылок на файл, имя владельца, имя группы, размер файла (в байтах), временной штамп и имя файла;
- `ls -la` — `-l`+`-a`
- `cd first-project` (от англ. *change directory*, «сменить директорию») — перейди в папку `first-project`;
- `cd first-project/html` — перейди в папку `html`, которая находится в папке `first-project`;
- `cd ..` — перейди на уровень выше, в родительскую папку;
- `cd ~` — перейди в домашнюю директорию (`/Users/Username`);
- `cd /` — перейди в корневую директорию.

<h2 id="git-file-id">Работа с файлами и папками</h2>

### Создание

- `touch index.html` (англ. *touch*, «коснуться») — создай файл `index.html` в текущей папке;
- `touch index.html style.css script.js` — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;
- `mkdir second-project` (от англ. *make directory*, «создать директорию») — создай папку с именем `second-project` в текущей папке.

### Копирование и перемещение

- `cp file.txt ~/my-dir` (от англ. *copy*, «копировать») — скопируй файл в другое место;
- `mv file.txt ~/my-dir` (от англ. *move*, «переместить») — перемести файл или папку в другое место.
- `clip < ~/.ssh/id_ed25519.pub` - Скопируй в буфер обмена всё содержимое файла `~/.ssh/id_ed25519.pub` 

### Чтение

- `cat file.txt` (от англ. *concatenate and print*, «объединить и распечатать») — распечатай содержимое текстового файла `file.txt`.

### Удаление

- `rm about.html` (от англ. *remove*, «удалить») — удали файл `about.html`;
- `rmdir images` (от англ. *remove directory*, «удалить директорию») — удали папку `images`;
- `rm -r second-project` (от англ. *remove*, «удалить» + *recursive*, «рекурсивный») — удали папку `second-project` и всё, что она содержит.

<h2 id="git-trck-id">Полезные возможности</h2>

- Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (`&&`).
- У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (`↑`) и вниз (`↓`).
- Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать `Tab`. Если файл или папка есть в текущей директории, командная строка допишет путь сама.

<h2 id="git-repo-id">Репозиторий</h2>

### Сделать папку репозиторием — `git init`

Чтобы Git начал отслеживать изменения в проекте, папку с файлами этого проекта нужно сделать Git-репозиторием (от англ. *repository* — «хранилище»). Для этого следует переместиться в неё и ввести команду `git init` (от англ. *initialize* — «инициализировать»).\
В зависимости от настроек Git может назвать начальную ветку или `main`, или `master`.\
Также `git init` выведет сообщение вида `Initialized empty Git repository in <*ваша папка с проектом*>/.git/` (англ. «инициализирован пустой Git-репозиторий в `<*ваша папка*>/.git/`»). В подпапке `.git` Git будет хранить всю служебную информацию.

### «Разгитить» папку, если что-то пошло не так, — `rm -rf .git`

Если вы случайно сделали Git-репозиторием не ту папку, её можно «разгитить». Для этого нужно удалить скрытую подпапку .git.

- ключ `-r` (от англ. *recursive* — «рекурсивно») позволяет удалять папки вместе с их содержимым;
- ключ `-f` (от англ. *force* — «заставить») избавит вас от вопросов вроде «Вы точно хотите удалить этот файл? А этот? И этот тоже?».

### Проверить состояние репозитория — `git status`

Команда `git status` выведет:

- название текущей ветки: `On branch master` или `On branch main`;
- сообщение о том, что в репозитории ещё нет коммитов: `No commits yet`;
- сообщение, которое говорит: «чтобы что-нибудь закоммитить (то есть зафиксировать), нужно сначала это создать» — `nothing to commit (create/copy files and use "git add" to track)`.

<h2 id="git-add-id">Подготовить файлы к сохранению — <code>git add</code></h2>

- `git add --all` (от англ. *add* — «добавить» + от англ. all — «всё»). Ключ, или флаг, `--all` позволяет подготовить к сохранению все файлы в репозитории.
- Добавлять файлы можно и по одному, без ключа `--all`.
- Также можно добавить текущую папку целиком — в этом случае все файлы в ней тоже будут добавлены. Обратиться к текущей папке в Bash позволяет точка (`.`).

<h2 id="git-comm-id">Коммит</h2>

Сделать коммит можно командой `git commit` c ключом `-m` (от англ. *message* — «сообщение»), который присваивает коммиту сообщение.\
Команда `git commit` выведет информацию о коммите.

- `[master (root-commit) baa3b6e]` значит:
    - коммит был в ветке `master`;
    - `root-commit` — это самый первый, или «корневой» (англ. *root*), коммит в ветке, у следующих коммитов такой надписи не будет;
    - `baa3b6e` — сокращённый идентификатор коммита.
- `2 files changed, 1 insertion(+)` значит:
    - изменились два файла;
    - одна строка была добавлена.
- Строки вида `create mode 100644 readme.txt` — это более подробная информация о новых (добавленных в Git) файлах.
    - `create` (англ. «создать») говорит, что файл был создан. Если бы файл был удалён, на этом месте было бы слово `delete` (англ. «удалить»).
    - `mode 100644` сообщает, что это обычный файл. Также возможны варианты `100755` для исполняемых файлов (например, `что-нибудь.exe`) и `120000` для файлов-ссылок в Linux. Файлы-ссылки не содержат данных сами по себе, а только ссылаются на другие файлы — как «ярлыки» в Windows.
 
<h2 id="git-log-id">Просмотреть историю коммитов — <code>git log</code></h2>

`git log` (от англ. *log* — «журнал \[записей\]») выводит коммиты в обратном хронологическом порядке — последние коммиты оказываются первыми сверху. 

Элементы, из которых состоит описание:
- строка из цифр и латинских букв после слова **commit** — это хеш коммита;
- **Author** — имя автора и его электронная почта;
- **Date** — дата и время создания коммита;
- в конце находится сообщение коммита.

Получить сокращённый лог можно с помощью команды `git log` с флагом `--oneline` (англ. «одной строкой»). В терминале появятся только первые несколько символов хеша каждого коммита и их комментарии.\
Сокращённый лог полезен, если в репозитории уже много коммитов — например, сотни или тысячи. В этом случае можно быстро найти нужный по описанию.\
Сокращённый хеш (то есть первые несколько символов полного) можно использовать точно так же, как и полный. Для этого команда `git log --oneline` автоматически подбирает такую длину сокращённых хешей, чтобы они были уникальными в пределах репозитория и Git всегда мог понять, о каком коммите идёт речь.

<h2 id="git-ssh-id">SSH</h2>

Когда компьютеры обмениваются данными в сети, они следуют сетевым протоколам (англ. *network protocols*) — правилам обмена данными между компьютерами.\
Один из наиболее распространённых сетевых протоколов — **SSH** (от англ. ***S**ecure **Sh**ell Protocol*). Он обеспечивает безопасный обмен данными в сети. С помощью этого протокола можно получать данные с удалённого компьютера или отправлять их на него. Трафик шифруется, поэтому протокол безопасен.

SSH использует пару ключей для обеспечения безопасности — публичный и приватный: 

- **Приватный ключ** (англ. *private key*) хранится только на вашем компьютере и не должен передаваться кому-либо ещё. Он используется для расшифровки данных.
- **Публичный ключ** (англ. *public key*) доступен всем и используется для шифрования данных. Они могут быть расшифрованы парным приватным ключом.

Только вы можете расшифровать данные с помощью приватного ключа, но любой владелец публичного ключа может их для вас зашифровать. Эти два ключа связаны и образуют SSH-пару.

По умолчанию директория с SSH-ключами находится в домашней директории пользователя. Обычно SSH-ключи находятся в директории `.ssh/`

### Инструкция по генерации SSH-ключа

1. Для генерации SSH-пары можно использовать программу `ssh-keygen`.
   ```bash
   $ ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"
   ```
   Если вы видите сообщение об ошибке, то, скорее всего, ваша система не поддерживает алгоритм шифрования `ed25519`.
   ```bash
   $ ssh-keygen -t rsa -b 4096 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"
   ```
1. Укажите место хранения ключей. Простой вариант — сделать домашний каталог пользователя путём по умолчанию. Для этого нажмите `Enter`.
   ```bash
   > Enter a file in which to save the key (C:\Users\<имя_пользователя>\.ssh\):[Press enter]
   ```
1. Программа запросит **кодовую фразу** (англ. *passphrase*) для доступа к SSH-ключу. Для этого нажмите `Enter`, а затем ещё раз `Enter` для подтверждения.
   ```bash
   > Enter passphrase (empty for no passphrase): [Type a passphrase]
   > Enter same passphrase again: [Type passphrase again]
   ```
   Многие пользователи Git не используют кодовую фразу для защиты своего SSH-ключа. Если такой фразы нет, то её не нужно вводить всякий раз при взаимодействии с удалённым репозиторием.
1. Связывание SSH-ключа и GitHub-аккаунта.
1. Проверьте правильность ключа с помощью следующей команды.
   ```bash
   $ ssh -T git@github.com
   ```
   Если это первый раз, когда вы используете Git, чтобы поделиться проектом на GitHub, появится похожее предупреждение.
   ```bash
   The authenticity of host 'github.com (140.82.121.4)' can't be established. ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU. This key is not known by any other names. Are you sure you want to continue connecting (yes/no/[fingerprint])?
   ```
   Это предупреждение сообщает, что вы никогда не соединялись с сервером GitHub. Поэтому Git не может гарантировать, что сервер является тем, за кого он себя выдаёт. Для подтверждения подлинности сервер генерирует и публикует ключи SHA256. Вы можете проверить ключи GitHub [по этой ссылке][GitHubSSHVerifyRef]. Если ключ в предупреждении совпадает с тем, что вы видите на сайте, значит, сервер является действительным. Введите `yes`, чтобы продолжить.

<h2 id="git-remo-id">Локальный и удалённый репозитории</h2>

### Привязать удалённый репозиторий к локальному — `git remote add`

Откройте консоль, перейдите в каталог локального репозитория и введите команду `git remote add` (от англ. *remote* — «удалённый» и *add* — «добавить»).
```bash
$ cd ~/dev/first-project
$ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git
```
Команде необходимо передать два параметра: имя удалённого репозитория и его URL. В качестве имени используйте слово `origin`.

### Убедиться, что репозитории связаны, — `git remote -v`

```bash
$ git remote -v
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (fetch)
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (push)
```
Флаг `-v` — короткая форма флага `--verbose` (англ. «подробный»). Он позволяет показать больше информации в выводе.

### Отправить изменения на удалённый репозиторий — `git push`

За это отвечает команда `git push` (от англ. *push* — «толкать»).\
В первый раз эту команду нужно вызвать с флагом `-u` и параметрами `origin` (имя удалённого репозитория) и `main` или `master` (название текущей ветки). Флаг `-u` свяжет локальную ветку с одноимённой удалённой.
```bash
$ git push -u origin main # Если команда приведёт к ошибке, попробуйте 
                          # заменить main на master.
```

<h2 id="git-hash-id">Хеш</h2>

**Хеширование** (от англ. *hash*, «рубить», «крошить», «мешанина») — это способ преобразовать набор данных и получить их «отпечаток» (англ. *fingerprint*).\
Информация о коммите — это набор данных: когда был сделан коммит, содержимое файлов в репозитории на момент коммита и ссылка на предыдущий, или **родительский** (англ. *parent*), коммит.\
Git хеширует (преобразует) информацию о коммите с помощью алгоритма **SHA-1** (от англ. ***S**ecure **H**ash **A**lgorithm* — «безопасный алгоритм хеширования») и получает для каждого коммита свой уникальный **хеш** — результат хеширования.\
Обычно хеш — это короткая (40 символов в случае SHA-1) строка, которая состоит из цифр 0—9 и латинских букв A—F (неважно, заглавных или строчных). Она обладает следующими важными свойствами:
- если хеш получить дважды для одного и того же набора входных данных, то результат будет гарантированно одинаковый;
- если хоть что-то в исходных данных поменяется (хотя бы один символ), то хеш тоже изменится (причём сильно).

### Хеш — основной идентификатор коммита

Git хранит таблицу соответствий `хеш → информация о коммите`. Если вы знаете хеш, вы можете узнать всё остальное: автора и дату коммита и содержимое закоммиченных файлов. Можно сказать, что хеш — основной идентификатор коммита.\
Их можно будет передавать в качестве параметра разным Git-командам, чтобы указать, с каким коммитом нужно произвести то или иное действие.\
Все хеши и таблицу `хеш → информация о коммите` Git сохраняет в служебные файлы. Они находятся в скрытой папке `.git` в репозитории проекта.\
Хеш коммита иожно узнать вызвав команду `git log`.

<h2 id="git-head-id">HEAD</h2>

Файл `HEAD` (англ. «голова», «головной») — один из служебных файлов папки `.git`. Он указывает на коммит, который сделан последним (то есть на самый новый).\
Внутри `HEAD` — ссылка на служебный файл: `refs/heads/master` (или `refs/heads/main` в зависимости от названия ветки). Если заглянуть в этот файл, можно увидеть хеш последнего коммита.\
Когда вы делаете коммит, Git обновляет `refs/heads/master` — записывает в него хеш последнего коммита. Получается, что `HEAD` тоже обновляется, так как ссылается на `refs/heads/master`.\
Если нужно передать последний коммит, то вместо его хеша можно просто написать слово `HEAD` — Git поймёт, что вы имели в виду последний коммит.

<h2 id="git-msg-id">Сообщения к коммитам</h2>

В выводе команды `git log --oneline` умещается максимум 72 первых символа сообщения, поэтому многие правила включают пункт: «Сообщение не должно быть длиннее 72 символов».\
Общие рекомендации по тому, как правильно составить сообщение. Оно должно быть:
- относительно коротким, чтобы его было легко прочитать;
- информативным.

### Корпоративный

Во многих компаниях применяется Jira — система для организации проектов и задач. У каждой задачи в Jira есть идентификатор из нескольких заглавных латинских букв и номера. Например, `LGS-239` значит, что это **239**-я задача в проекте **LGS** (сокращение от англ. _**l**o**g**istic**s**_ — «логистика»).\
В корпоративном стиле в начале сообщения обычно указывают Jira-ID, а после — текст сообщения.
```bash
$ git commit -m "LGS-239: Дополнить список пасхалок новыми числами"
```

### Conventional Commits

#### Summary

The Conventional Commits specification is a lightweight convention on top of commit messages. It provides an easy set of rules for creating an explicit commit history; which makes it easier to write automated tools on top of. This convention dovetails with [SemVer][SVRef], by describing the features, fixes, and breaking changes made in commit messages.\
The commit message should be structured as follows:
```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```
The commit contains the following structural elements, to communicate intent to the consumers of your library:
1. **fix:** a commit of the _type_ `fix` patches a bug in your codebase (this correlates with [`PATCH`][SVRef] in Semantic Versioning).
1. **feat:** a commit of the _type_ `feat` introduces a new feature to the codebase (this correlates with [`MINOR`][SVRef] in Semantic Versioning).
1. **BREAKING CHANGE:** a commit that has a footer `BREAKING CHANGE:`, or appends a `!` after the type/scope, introduces a breaking API change (correlating with [`MAJOR`][SVRef] in Semantic Versioning). A BREAKING CHANGE can be part of commits of any _type_.
1. _types_ other than `fix:` and `feat:` are allowed, for example [@commitlint/config-conventional][commitlintCCRef] (based on the [Angular convention][AngCRef]) recommends `build:`, `chore:`, `ci:`, `docs:`, `style:`, `refactor:`, `perf:`, `test:`, and others.
1. _footers_ other than `BREAKING CHANGE: <description>` may be provided and follow a convention similar to [git trailer format][gtfRef].

Additional types are not mandated by the Conventional Commits specification, and have no implicit effect in Semantic Versioning (unless they include a BREAKING CHANGE). A scope may be provided to a commit’s type, to provide additional contextual information and is contained within parenthesis, e.g., `feat(parser): add ability to parse arrays`.

<details>
<summary><h4>Examples</h4></summary>
  
##### Commit message with description and breaking change footer

```
feat: allow provided config object to extend other configs

BREAKING CHANGE: `extends` key in config file is now used for extending other config files
```

##### Commit message with `!` to draw attention to breaking change

```
feat!: send an email to the customer when a product is shipped
```

##### Commit message with scope and `!` to draw attention to breaking change

```
feat(api)!: send an email to the customer when a product is shipped
```

##### Commit message with both `!` and BREAKING CHANGE footer

```
chore!: drop support for Node 6

BREAKING CHANGE: use JavaScript features not available in Node 6.
```

##### Commit message with no body

```
docs: correct spelling of CHANGELOG
```

##### Commit message with scope

```
feat(lang): add Polish language
```

##### Commit message with multi-paragraph body and multiple footers

```
fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Remove timeouts which were used to mitigate the racing issue but are
obsolete now.

Reviewed-by: Z
Refs: #123
```

</details>

#### [Specification][CCSpecRef]

### GitHub-стиль

GitHub можно использовать не только для хранения файлов проекта, но и для ведения списка **задач** (англ. _issue_) этого проекта. Если коммит «закрывает» или «решает» какую-то задачу, то в его сообщении удобно указывать ссылку на неё. Для этого в любом месте сообщения нужно указать `#<номер задачи>`. Например, вот так.
```bash
$ git commit -m "Исправить #334, добавить график температуры"

$ git commit -m "Close #334, добавить график температуры"
```

> ### Инфинитив и императив
> 
> > Для сообщений на русском языке часто рекомендуют использовать инфинитивы.
> > 
> > Например: `Добавить тесты для PipkaService`, `Исправить ошибку #123` и так далее.
>
> > Для сообщений на английском рекомендуется использовать **повелительное наклонение** (англ. _imperative_).
> > 
> > Например: `Use library mega_lib_300`, `Fix exit button` и так далее.

<h2 id="git-stat-id">Статусы файлов в Git</h2>

### Статусы `untracked`/`tracked`, `staged` и `modified`

Одна из ключевых задач Git — отслеживать изменения файлов в репозитории. Для этого каждый файл помечается каким-либо статусом.
- `untracked` (англ. «неотслеживаемый»)\
  Новые файлы в Git-репозитории помечаются как `untracked`, то есть неотслеживаемые. Git «видит», что такой файл существует, но не следит за изменениями в нём. У `untracked`-файла нет предыдущих версий, зафиксированных в коммитах или через команду `git add`.
- `staged` (англ. «подготовленный»)\
  После выполнения команды `git add` файл попадает в **staging area** (от англ. _stage_ — «сцена», «этап \[процесса\]» и _area_ — «область»), то есть в список файлов, которые войдут в коммит. В этот момент файл находится в состоянии `staged`.
  > #### Staging area, index и cache
  >
  > > Staging area также называют **index** (англ. «каталог») или **cache** (англ. «кеш»), а состояние файла `staged` иногда называют `indexed` или `cached`.
- `tracked` (англ. «отслеживаемый»)\
  Состояние `tracked` — это противоположность `untracked`. Оно довольно широкое по смыслу: в него попадают файлы, которые уже были зафиксированы с помощью `git commit`, а также файлы, которые были добавлены в staging area командой `git add`. То есть все файлы, в которых Git так или иначе отслеживает изменения.
- `modified` (англ. «изменённый»)\
  Состояние `modified` означает, что Git сравнил содержимое файла с последней сохранённой версией и нашёл отличия. Например, файл был закоммичен и после этого изменён.

> Для файлов в состояниях `staged` и `modified` обычно не указывают, что они также `tracked`, потому что это состояние подразумевается.

### Про `staged` и `modified`

Команда `git add` добавляет в staging area только текущее содержимое файла. Если вы, например, сделаете `git add file.txt`, а затем измените `file.txt`, то новое содержимое файла не будет находиться в staging.

Git сообщит об этом с помощью статуса `modified`: файл изменён относительно той версии, которая уже в staging. Чтобы добавить в staging последнюю версию, нужно выполнить `git add file.txt` ещё раз.

### Типичный жизненный цикл файла в Git

```mermaid
%%{init: { 'logLevel': 'debug', 'theme': 'dark', 'gitGraph': {'showBranches': true, 'showCommitLabel':true,'mainBranchName': 'untracked'}} }%%
    gitGraph
        commit id: "touch file.txt" tag: "file.txt"
        branch staged
        commit id: "git add file.txt" tag: "file.txt"
        branch modified
        commit id: "vim file.txt" tag: "file.txt"
        checkout staged
        commit id: " " type: REVERSE tag: "file.txt"
        merge modified
        commit id: "git add file.txt " tag: "file.txt"
        branch tracked
        commit id: "git commit" tag: "file.txt"
        checkout modified
        commit id: "  " type: HIGHLIGHT
        merge tracked
        commit id: "vim file.txt " tag: "file.txt"
        checkout staged
        commit id: "    " type: HIGHLIGHT
        merge modified
        commit id: "git add file.txt  " tag: "file.txt"
        checkout tracked
        commit id: "   " type: HIGHLIGHT
        merge staged
        commit id: "git commit " tag: "file.txt"
```

1. Файл только что создали. Git ещё не отслеживает содержимое этого файла. Состояние: `untracked`.
1. Файл добавили в staging area с помощью `git add`. Состояние: `staged` (+ `tracked`).
   - Возможно, изменили файл ещё раз. Состояния: `staged`, `modified` (+ `tracked`).\
     `staged` и `modified` у одного файла, но у разных его версий.
   - Ещё раз выполнили `git add`. Состояние: `staged` (+ `tracked`).
1. Сделали коммит с помощью `git commit`. Состояние: `tracked`.
2. Изменили файл. Состояние: `modified` (+ `tracked`).
3. Снова добавили в staging area с помощью `git add`. Состояния: `staged` (+ `tracked`).
4. Сделали коммит. Состояния: `tracked`.

____________________________________________________________________________________________________________________________________________________________
<h1 id="python-id">The Zen of Python</h1>

<details>
<summary>Image</summary>

![zenPy][zenPyImg]

</details>

## PyCharm Shortcuts







[GitHubMCSRef]: https://gist.github.com/fomvasss/8dd8cd7f88c67a4e3727f9d39224a84c "GitHub"
[MCSRef]: https://www.markdownguide.org/cheat-sheet/ "Markdown"
[linguistRef]: https://github.com/github-linguist/linguist/blob/master/lib/linguist/languages.yml
[zenPyImg]: https://github.com/KeTavWork/PyStuff/blob/master/zenPy.png
[MTGRef]: https://www.tablesgenerator.com/markdown_tables
[AWDMEFer]: https://anywaydata.com/
[GitHubSSHVerifyRef]: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints
[SVRef]: https://semver.org/
[commitlintCCRef]: https://github.com/conventional-changelog/commitlint/tree/master/%40commitlint/config-conventional
[AngCRef]: https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#-commit-message-guidelines
[gtfRef]: https://git-scm.com/docs/git-interpret-trailers
[CCSpecRef]: https://www.conventionalcommits.org/en/v1.0.0/#specification
[mermaidRef]: http://mermaid.js.org/
