---
date: 2016-09-21
categories: [it, program]
tags: [Atom, Текстовой редактор, FAQ]
update: 2018-11-24
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2016/blob/main/faq-atom/faq-atom.md
---

# Настройка Atom

Обновленная в 2018 году статья по настройке Atom.

## Введение

Первым продвинутым блокнотом, которым я начал активно пользоваться, был [Notepad++](https://github.com/Harrix/harrix.dev-blog-2013/blob/main/faq-notepad-plus-plus/faq-notepad-plus-plus.md) (до сих пор им часто пользуюсь), потом пытался перейти на [Sublime Text](https://github.com/Harrix/harrix.dev-blog-2013/blob/main/faq-sublime-text-2/faq-sublime-text-2.md). А потом пробовал перейти на Atom, про который говорится в этой статье.

И да. Потом я всё равно перешел на Visual Studio Code.

## Установка

Скачиваем либо официальную последнюю версию с [сайта](https://atom.io/), либо текущую последнюю версию y в [GitHub](https://github.com/atom/atom/releases):

![Скачивание программы](img/download.png)

Запускаем скаченный файл, и он автоматически запустит установку без всяких диалоговых окон, но Windows может поругаться (но мы скачивали с официального репозитория):

![Предупреждение от Windows](img/install_01.png)

![Предупреждение от Windows](img/install_02.png)

![Установка Atom](img/install_03.png)

После установки откроется редактор, где снимаем галочку, чтобы при каждом старте не показывалось приветственное окно, а также соглашаемся, чтобы правильно открывались ссылки `atom:\\`:

![Редактор Atom](img/install_04.png)

## Первоначальная настройка

Перейдем в настройки приложения `File` → `Settings`:

![Настройки программы](img/settings.png)

Снимаем галочку с пункта `Open Empty Editor On Start` в разделе `Core`, чтобы при запуске программы открывались последние открытые файлы:

![Изменение параметра «Open Empty Editor On Start»](img/config_01.png)

Также в разделе `Core` можно указать папку ваши основных проектов:

![Выбор папки с проектами](img/config_02.png)

В разделе `Editor` включаем переносы строк `Soft Wrap`:

![Включение переноса строк](img/config_03.png)

В этом же разделе можно указать сколько пробелов будет ставиться при нажатии на табуляцию:

![Выбор количества пробелов для табуляции](img/config_04.png)

## Открытие файлов и каталогов через контекстное меню

Идем `File` → `Settings`.

В разделе `System` добавляем в контекстном меню возможность открывать файлы и папки с помощью Atom:

![Настройка контекстного меню](img/config_05.png)

Сейчас в 2018 году всё работает отлично, но раньше в 2016 году у меня эта команда не помогла, поэтому добавлял вручную в реестр Windows 10. Поэтому, если у вас не работает, то читайте ниже:

Для этого создайте текстовой файл расширения `.reg` (например, `open-w-atom.reg`) с подобным содержанием:

```reg
Windows Registry Editor Version 5.00

; when you right click a file
[HKEY_CLASSES_ROOT\*\shell\Atom KI ext]
""="Open File in Atom"
"Icon"="C:\\Users\\sensor\\AppData\\Local\\atom\\app-1.11.0-beta5\\atom.exe"

[HKEY_CLASSES_ROOT\*\shell\Atom KI ext\command]
""="C:\\Users\\sensor\\AppData\\Local\\atom\\app-1.11.0-beta5\\atom.exe \"%1\""

; when you right click a folder
[HKEY_CLASSES_ROOT\Directory\shell\Atom KI ext]
""="Open Folder in Atom"
"Icon"="C:\\Users\\sensor\\AppData\\Local\\atom\\app-1.11.0-beta5\\atom.exe"

[HKEY_CLASSES_ROOT\Directory\shell\Atom KI ext\command]
""="C:\\Users\\sensor\\AppData\\Local\\atom\\app-1.11.0-beta5\\atom.exe \"%1\""

; when you right click a folder while holding shift
[HKEY_CLASSES_ROOT\Directory\Background\shell\Atom KI ext]
""="Open Folder in Atom"
"Icon"="C:\\Users\\sensor\\AppData\\Local\\atom\\app-1.11.0-beta5\\atom.exe"

[HKEY_CLASSES_ROOT\Directory\Background\shell\Atom KI ext\command]
""="C:\\Users\\sensor\\AppData\\Local\\atom\\app-1.11.0-beta5\\atom.exe \"%V\""

; when you right click the background, not on a particular file or folder.
[HKEY_CLASSES_ROOT\LibraryFolder\Background\shell\Atom KI ext]
""="Open Folder in Atom"
"Icon"="C:\\Users\\sensor\\AppData\\Local\\atom\\app-1.11.0-beta5\\atom.exe"

[HKEY_CLASSES_ROOT\LibraryFolder\Background\shell\Atom KI ext\command]
""="C:\\Users\\sensor\\AppData\\Local\\atom\\app-1.11.0-beta5\\atom.exe \"%V\""
```

Везде текст `C:\\Users\\sensor\\AppData\\Local\\atom\\app-1.11.0-beta5\\atom.exe` поменяйте на путь к программе на вашем компьютере. Он будет обязательно другой у вас. И обратите внимание, что в пути у вас должны быть двойные слэши.

После этого запустите сохраненный файл и внесите изменения в реестр. После этого у вас в контекстном меню у файлов и папок появятся такие подобные пункты:

![Контекстное меню для директории](img/context-menu_01.png)

![Контекстное меню для файла](img/context-menu_02.png)

## Выбор темы оформления (Material Design)

Идем `File` → `Settings`. И там идет в раздел `Themes`:

![Раздел с настройками тем](img/config_06.png)

Там можно выбрать тему для оформления интерфейса Atom, а также для отображения непосредственно текста в документах:

![Выбор тем](img/config_07.png)

Вот не люблю я темные темы для текстовых редакторов. Поэтому выбирал светлые темы:

![Светлые темы](img/config_08.png)

Вот так будет выглядеть редактор с такими темами:

![Внешний вид редактора со светлыми темами](img/config_09.png)

Если вы хотите найти и установить другие темы, то перейдите в раздел установки, а там выберете `Themes` для перехода в поиск тем:

![Установка новых тем](img/config_10.png)

Например, популярны темы в стиле `Material Design`:

![Пример поиска тем](img/config_11.png)

Выбранные темы можно установить.

Я себе установил `atom-material-ui` и `atom-material-syntax-light`.

И они потом появятся в выборе тем:

![Установленные темы](img/config_12.png)

Темы также имеют варианты настроек:

![Переход к настройкам темы](img/config_13.png)

Я поменял основной цвет темы:

![Выбор основного цвета темы](img/config_14.png)

Сделал компактный вид панели вкладок:

![Вкладки становятся компактными](img/config_15.png)

После этих настроек редактор выглядит так:

![Внешний вид редактора](img/config_16.png)

## Проверка орфографии на английском и русском языках

Идем `File` → `Settings`. Там идет в пакеты `Packages`.

В поиске установленных пакетов выбираем `spell`.

И в пакете `spell-checker` переходим в настройки:

![Настройки проверки орфографии](img/config_17.png)

И в разделе `Locales` напишите `en-US, ru-RU`:

![Выбор языков для проверки орфографии](img/config_18.png)

После этого появится проверка орфографии одновременно английского и русского языка в документах (обратите внимание, что в Windows должны быть установлены соответствующие языки, так как базу Atom берет оттуда):

![Пример проверки орфографии](img/config_19.png)

Также в настройках поставьте галочку около `Add Known Words`. Тогда вам будет предлагаться добавлять новые слова в словарь:

![Выбор пункта «Add Known Words»](img/config_20.png)

Вызов подсказок о том, как можно исправить слово, делается через `Ctrl` + `Shift` + `:`:

![Подсказки для исправления слова](img/config_21.png)

Не для всех расширений файлов включается проверка орфографии. Чтобы подключить проверку в орфографии для файлов нового расширения, вызовете консоль `Ctrl` + `Shift` + `P`, находясь в файле. Там пропишите `Editor: Log Cursor Scope` и выберете этот пункт. И вы увидите внизу справа уведомление с одним или несколькими пунктами текста. Один из них будет означать тип документа. Копируем этот тип и закрываем уведомление. Потом идем в настройки нашего пакета проверки орфографии. И в разделе `Grammars` дописываем наш тип файлов:

![Список проверяемых типов файлов](img/config_22.png)

## Установка пакетов

Идем `File` → `Settings`. И там идет в раздел `Install`, и там выбираем `Packages`:

![Окно установки пакетов](img/config_23.png)

Пишем название пакета, который нам нужен, нажимаем `Enter`. И после появление списка плагинов устанавливаете тот, что вам нужен:

![Установка пакета](img/config_24.png)

Установленный пакет появится в списке пакетов:

![Установленный пакет](img/config_25.png)

## Настройка предустановленных пакетов

Идем `File` → `Settings`. И там идет в раздел `Packages`.

Находим там пакет `tree-view`. И переходим в настройки его:

![Пакет tree-view](img/config_26.png)

И там ставим галочку около `Hide Ignored Names`. Например, чтобы в дереве папок не показывалась папка `.git`, которая нам не понабиться:

![Включение параметра «Hide Ignored Names»](img/config_27.png)

А в пакете `autosave` можно включить автоматическое сохранение документов, когда Atom теряет фокус. Это не касается документов, которые были созданы, но еще ни разу не сохранялись. В общем полезная вещь:

![Включение автосохранения](img/config_28.png)

## Установленные пакеты у меня

Список тех пакетов, которые я дополнительно установил.

- [minimap](https://atom.io/packages/minimap) — карта документа справа от документа с возможностью прокрутки документа:

![Пакет minimap](img/minimap.png)

- [pigments](https://atom.io/packages/pigments) — для отображения цветов там, где мы их обозначаем в коде:

![Пакет pigments](img/pigments.png)

- [color-picker](https://atom.io/packages/color-picker) — теперь цвет можно менять через пипетку `Ctrl` + `Alt` + `C`:

![Пакет color-picker](img/color-picker.png)

- [file-icons](https://atom.io/packages/file-icons) — иконки для файлов в списке файлов:

![Пакет file-icons](img/file-icons.png)

- [language-qml](https://atom.io/packages/language-qml) — подсветка синтаксиса для файлов `.qml`:

![Пакет language-qml](img/language-qml.png)

- [language-ini](https://atom.io/packages/language-ini) — подсветка синтаксиса для файлов `.ini`.

- [language-latex](https://atom.io/packages/language-latex) — для отображения LaTeX кода:

![Пакет language-latex](img/language-latex.png)

- [highlight-selected](https://atom.io/packages/highlight-selected) — Если выделили слово, то в других местах это же слово будет подсвечиваться:

![Пакет highlight-selected](img/highlight-selected.png)

- [minimap-highlight-selected](https://atom.io/packages/minimap-highlight-selected) — дополнение к предыдущему пакету. Теперь подсветка выделяемого слова будет и в карте документа справа:

![Пакет minimap-highlight-selected](img/minimap-highlight-selected.png)

- [sort-lines](https://atom.io/packages/sort-lines) — сортировка текста по `F5`. А если войти в консоль `Ctrl` + `Shift` + `P` и там набрать `Sort`, то увидите, что есть еще команды для работы с текстом по сортировке:

![Пакет sort-lines](img/sort-lines_01.png)

Команда `Sort lines: Natural` сортирует числа как числа:

![Сортировка чисел](img/sort-lines_02.png)

- [export-html](https://atom.io/packages/export-html) — печать документа с подсветкой синтаксиса. Переходим в консоль и там набираем `export` и выбираем нашу команду:

![Пакет export-html](img/export-html_01.png)

![Печать документа с подсветкой синтаксиса](img/export-html_02.png)

- [pdf-view](https://atom.io/packages/pdf-view) — для просмотра PDF документов:

![Пакет pdf-view](img/pdf-view.png)

- [svg-preview](https://atom.io/packages/svg-preview) — превью SVG файлов:

![Пакет svg-preview](img/svg-preview.png)

- [atom-beautify](https://atom.io/packages/atom-beautify) — красиво расставляет отступы в коде по сочетанию `Ctrl` + `Alt` + `B`.

Было:

![Код HTML до преобразований](img/atom-beautify_01.png)

Стало:

![Код HTML после преобразований](img/atom-beautify_02.png)

Плагин поддерживает много разных языков, но для поддержки некоторых нужно пошаманить. Например, для C++ программа выдает такое предупреждение: `Could not find 'uncrustify'. The program may not be installed.`:

![Сообщение об ошибке](img/atom-beautify_03.png)

Вам нужно установить программу `uncrustify`.

Для этого идете по адресу <https://sourceforge.net/projects/uncrustify/>.

Скачивайте файл, разархивируйте проект. Там найдете файл `uncrustify.exe`.

Теперь нужно, чтобы в глобальной переменной `PATH` в Windows был путь к данному файлу. Самое простое — это скопировать файл в папку Windows (`C:\Windows`).

После этого поддержка C++ в Atom будет осуществлена.

Было:

![Код C++ до преобразований](img/atom-beautify_04.png)

Стало:

![Код C++ после преобразований](img/atom-beautify_05.png)

Подробно посмотреть на список поддерживаемых языков и того, что может пригодится, можно тут: <https://atom.io/packages/atom-beautify>.

- [simple-drag-drop-text](https://atom.io/packages/simple-drag-drop-text) — позволяет перетаскивать текст, как в любом другом редакторе:

[Пакет simple-drag-drop-text](img/simple-drag-drop-text.mp4)

- [multi-wrap-guide](https://atom.io/packages/multi-wrap-guide) — по умолчанию в редакторе стоит вертикальная линия обозначающая 80 символов в строке. Но сейчас много где (например, в Qt) используется длина строки в 120 символов. С помощью этого плагина можно добавить еще вертикальные линии:

![Пакет multi-wrap-guide](img/multi-wrap-guide.png)

- [indent-guide-improved](https://atom.io/packages/indent-guide-improved) — подсвечивает блоки кода, чтобы можно было понять, где вы сейчас находитесь.

Правда для моей темы черная линия выглядит не сильно красиво, поэтому в настройках перейдем в ручное управление настройками:

![Настройки Atom](img/indent-guide-improved_01.png)

Там открываем `styles.less`:

![Файл настроек внешнего вида Atom](img/indent-guide-improved_02.png)

И там добавляем такой текст, например:

```less
.indent-guide-improved {
  background-color: #eef1f2;
  &.indent-guide-stack {
    background-color: #19a5a5;
    &.indent-guide-active {
      background-color: #19a5a5;
    }
  }
}
```

![Код оформления линий из пакета indent-guide-improved](img/indent-guide-improved_03.png)

Сохраняем файл.

В итоге получаем вот такое:

![Пакет indent-guide-improved](img/indent-guide-improved_04.png)

- [advanced-open-file](https://atom.io/packages/advanced-open-file) — через `Ctrl` + `Alt` + `O` открываем файлы и их создаем, открываем папки без диалоговых системных окон:

![Пакет advanced-open-file](img/advanced-open-file.png)

- [open-in-browsers](https://atom.io/packages/open-in-browsers) — люблю в Notepad++ открывать HTML файлы прямо из редактора. Здесь это решается этим плагином:

![Пакет open-in-browsers](img/open-in-browsers.png)

- [auto-encoding](https://atom.io/packages/auto-encoding) — автоматически определяет кодировку файла. Крайне полезная вещь в мире, где еще не все текстовые файлы находятся в кодировке Юникод:

![Пакет auto-encoding](img/auto-encoding.png)

- [split-diff](https://atom.io/packages/split-diff) — позволяет сравнивать два файла.

- [minimap-split-diff](https://atom.io/packages/minimap-split-diff) — дополнение к предыдущему пакету, чтобы изменения отображались и на миникарте.

Итак, как производить сравнения файлов. Один из двух файлов отправляем во вторую панель:

![Открытие второй панели открытия файлов](img/split-diff_01.png)

В первой вкладке открываем второй файл:

![Открытие первого файла](img/split-diff_02.png)

Вызываем консоль `Ctrl` + `Shift` + `P`. Там пишем `Split`.

Выбираем команду `Split Diff: Enabled`:

![Выбор команды «Split Diff: Enabled»](img/split-diff_03.png)

У нас синхронизировались две панели и показываются изменения файлов:

![Результат сравнения двух файлов](img/split-diff_04.png)

- [tab-switcher](https://atom.io/packages/tab-switcher) — переключение между вкладками с помощью `Alt` + `[` и `Alt` + `]`:

![Пакет tab-switcher](img/tab-switcher.png)

- [fold-lines](https://atom.io/packages/fold-lines) — при сворачивании блока показывает заметную линию:

![Пакет fold-lines](img/fold-lines.png)

- [path-copy](https://atom.io/packages/path-copy) — в контекстном меню во вкладке появляется возможность скопировать путь к файлу, имени файлу и так далее. В Notepad++ постоянно этим пользовался:

![Пакет path-copy](img/path-copy.png)

- [markdown-writer](https://atom.io/packages/markdown-writer) команды для работы с markdown файлами:

![Пакет markdown-writer](img/markdown-writer.png)

- [tool-bar](https://atom.io/packages/tool-bar) — панель инструментов. Сам по себе данный плагин ничего не делает, а предназначен для других плагинов, которые создают панель инструментов. Так как кнопок будет много, то размер кнопок выставим маленькими:

![Настройки пакета tool-bar](img/tool-bar.png)

- [flex-tool-bar](https://atom.io/packages/flex-tool-bar) — данный плагин служит для настройки предыдущего плагина, где вы можете гибко создать свою панель инструментов.

При установке плагина появляется пустая панель инструментов с одной кнопкой, которая открывает файл, в котором будем прописывать наши кнопки:

![Пакет flex-tool-bar](img/flex-tool-bar_01.png)

Я прописал вот такие кнопки:

```js
# This file is used by Flex Tool Bar to create buttons on your Tool Bar.
# For more information how to use this package and create your own buttons,
#   read the documentation on https://atom.io/packages/flex-tool-bar

[
    {
        type: "button"
        icon: 'file-tree'
        iconset: 'mdi'
        callback: "tree-view:toggle"
        tooltip: "Toggle Sidebar"
    }
    {
        type: "button"
        icon: 'file-outline'
        iconset: 'mdi'
        callback: "application:new-file"
        tooltip: "New File"
    }
    {
        type: "button"
        icon: 'file'
        iconset: 'mdi'
        callback: "advanced-open-file:toggle"
        tooltip: "Open File"
    }
    {
        type: "button"
        icon: 'content-save'
        iconset: 'mdi'
        callback: "core:save"
        tooltip: "Save File"
    }
    {
        type: "button"
        icon: 'content-save-all'
        iconset: 'mdi'
        callback: "window:save-all"
        tooltip: "Save All"
    }
    {
        type: "button"
        icon: 'printer'
        iconset: 'mdi'
        callback: "export-html:export"
        tooltip: "Print"
    }
    {
        type: "button"
        icon: 'magnify'
        iconset: 'mdi'
        callback: "find-and-replace:toggle"
        tooltip: "Find"
    }
    {
        type: "button"
        icon: 'folder-multiple-outline'
        iconset: 'mdi'
        callback: "project-find:show"
        tooltip: "Find In Project"
    }
    {
        type: "button"
        icon: 'auto-fix'
        iconset: 'mdi'
        callback: "atom-beautify:beautify-editor"
        tooltip: "Beautify"
    }
    {
        type: "button"
        icon: 'image-filter-hdr'
        iconset: 'mdi'
        callback: "svg-preview:toggle"
        tooltip: "SVG Preview"
    }
    {
        type: "button"
        icon: 'google-chrome'
        iconset: 'mdi'
        callback: "open-in-browsers:Chrome"
        tooltip: "Open in Chrome"
    }
    {
        type: "button"
        icon: 'eyedropper-variant'
        iconset: 'mdi'
        callback: "color-picker:open"
        tooltip: "Color Picker"
    }
    {
        type: "button"
        icon: 'function'
        iconset: 'mdi'
        callback: "symbols-view:toggle-file-symbols"
        tooltip: "Functions"
    }
    {
        type: "button"
        icon: 'code-equal'
        iconset: 'mdi'
        callback: "split-diff:enable"
        tooltip: "Split Diff"
    }
    {
        type: "button"
        icon: 'format-textdirection-l-to-r'
        iconset: 'mdi'
        callback: "window:toggle-invisibles"
        tooltip: "Show All Characters"
    }
    {
        type: "button"
        icon: 'sort-alphabetical'
        iconset: 'mdi'
        callback: "sort-lines:sort"
        tooltip: "Sort"
    }
    {
        type: "button"
        icon: 'sort-numeric'
        iconset: 'mdi'
        callback: "sort-lines:natural"
        tooltip: "Sort Natural"
    }
    {
        type: "button"
        icon: 'arrow-up-bold'
        iconset: 'mdi'
        callback: "editor:upper-case"
        tooltip: "Upper Case"
    }
    {
        type: "button"
        icon: 'arrow-down-bold'
        iconset: 'mdi'
        callback: "editor:lower-case"
        tooltip: "Lower Case"
    }
    {
        type: "button"
        icon: 'spellcheck'
        iconset: 'mdi'
        callback: "spell-check:correct-misspelling"
        tooltip: "Correct Misspelling"
    }
    {
        type: "button"
        icon: 'lock'
        iconset: 'mdi'
        callback: "editor:toggle-line-comments"
        tooltip: "Commenting Out Code"
    }
    {
        type: "button"
        icon: 'console'
        iconset: 'mdi'
        callback: "command-palette:toggle"
        tooltip: "Command Palette"
    }
    {
        type: "spacer"
    }
    {
        type: "button"
        icon: 'markdown'
        iconset: 'mdi'
        callback: "markdown-preview:toggle"
        tooltip: "Markdown Preview"
    }
    {
        type: "button"
        icon: 'code-tags'
        iconset: 'mdi'
        callback: "markdown-writer:toggle-codeblock-text"
        tooltip: "Code"
    }
    {
        type: "button"
        icon: 'link-variant'
        iconset: 'mdi'
        callback: "markdown-writer:insert-link"
        tooltip: "Insert Link"
    }
    {
        type: "button"
        icon: 'image'
        iconset: 'mdi'
        callback: "markdown-writer:insert-image"
        tooltip: "Insert Image"
    }
    {
        type: "button"
        icon: 'format-bold'
        iconset: 'mdi'
        callback: "markdown-writer:toggle-bold-text"
        tooltip: "Bold"
    }
    {
        type: "button"
        icon: 'format-italic'
        iconset: 'mdi'
        callback: "markdown-writer:toggle-italic-text"
        tooltip: "Italic"
    }
    {
        type: "button"
        icon: 'format-list-bulleted'
        iconset: 'mdi'
        callback: "markdown-writer:toggle-ul"
        tooltip: "Unordered List"
    }
    {
        type: "button"
        icon: 'format-list-numbers'
        iconset: 'mdi'
        callback: "markdown-writer:toggle-ol"
        tooltip: "Ordered List"
    }
    {
        type: "button"
        icon: 'format-header-1'
        iconset: 'mdi'
        callback: "markdown-writer:toggle-h1"
        tooltip: "Heading 1"
    }
    {
        type: "button"
        icon: 'format-header-2'
        iconset: 'mdi'
        callback: "markdown-writer:toggle-h2"
        tooltip: "Heading 2"
    }
    {
        type: "button"
        icon: 'format-header-3'
        iconset: 'mdi'
        callback: "markdown-writer:toggle-h3"
        tooltip: "Heading 3"
    }
    {
        type: "button"
        icon: 'table'
        iconset: 'mdi'
        callback: "markdown-writer:insert-table"
        tooltip: "Insert Table"
    }
    {
        type: "button"
        icon: 'table-edit'
        iconset: 'mdi'
        callback: "markdown-writer:format-table"
        tooltip: "Format Table"
    }
]
```

![Полная панель команд](img//flex-tool-bar-2.png)

Панель у меня получилась большой. Скорее всего многие команды вам не понадобятся. Также многие команды не будут запускаться, если вы не установили некоторые плагины (список плагинов, что тут написан — полный).

Разумеется, что вы можете прописать свои команды, какие вам будут нужны.

Обратите внимание на то, что многие команды пакетов доступны и из главного меню:

![Команды пакетов](img/commands.png)

## Как вызвать командную строку Atom

Через `Ctrl` + `Shift` + `P`:

![Командная строка](img/command-line.png)

## Как поменять язык подсветки синтаксиса кода

Внизу справа имеется возможность поменять подсветку синтаксиса:

![Выбор языка подсветки синтаксиса](img/syntax-highlighting-language.png)

## Как найти файл в папке проекта по его имени

Через `Ctrl` + `P`:

![Список файлов](img/file-by-name.png)

## Как второй документ отобразить рядом с первым документом

Эта функция часто используется в Notepad++. Тут она тоже есть: правая кнопка по вкладке с документом и выбираем, куда продублировать документ. Единственный минус, что в первой области документ остается открытым тоже, но его там можно просто закрыть:

![Разделить на две области](img/split-right_01.png)

![Файл отображается во второй области справа](img/split-right_02.png)

## Как сворачивать код

Подведите курсор на номера строк. И там появятся стрелочки, нажимая на которые, код свернется:

![Несвернутый код](img/folding_01.png)

![Свернутый код](img/folding_02.png)

## Как найти что-то в файле

Делается через стандартное сочетание клавиш `Ctrl` + `F`. Также там отображается число найденных мест:

![Панель поиска](img/find.png)

## Как заменить что-то в файле

Аналогично через `Ctrl` + `F`:

![Функции по замещению текста в панели поиска](img/replace.png)

## Как найти в файлах всей папки

Делается через сочетание клавиш `Shift` + `Ctrl` + `F`. Замена во всех файлах проекта также делается:

![Поиск в директории](img/find-in-folder_01.png)

Можно также там задавать фильтр для файлов, по которым производится поиск:

![Поле для фильтра поиска](img/find-in-folder_02.png)

## Как показать невидимые символы

Входим в консоль `Ctrl` + `Shift` + `P` и там набираем `invisibles` (или часть строки) и выбираем команду `Window: Toggle Invisibles` и её выбираем.

Отмена показа невидимых символов осуществляется аналогичным способом:

![Показ невидимых символов](img/invisibles.png)

## Как продублировать текущую строку

Через `Ctrl` + `Shift` + `D`:

![Дублирование строки](img/duplicate-line.png)

## Как закомментировать выделенные строчки

Через `Ctrl` + `/`:

![Комментирование строк](img/comment-lines.png)

## Как объединить выделенные строки в одну

Через `Ctrl` + `J`:

![Объединение строк в одну(img/join-lines.png)

## Как ставить около строк отметки «bookmarks»

Через `Ctrl` + `Alt` + `F2`.

Переход между отметками осуществляется через `F2`:

![Отмеченные строки в коде](img/bookmarks.png)

## Как вызвать автодополнение принудительно

Через `Ctrl` + `Space`:

![Автодополнение кода](img/autocomplete.png)

## Как сделать все буквы заглавными/маленькими в выделенном тексте

Через `Ctrl` + `K` + `U`, чтоб все буквы стали большими:

![Приведение букв к верхнему регистру](img/upper.png)

Через `Ctrl` + `K` + `L`, чтоб все буквы стали маленькими:

![Приведение букв к нижнему регистру](img/lower.png)

## Как перейти к соответствующей скобке (открывающейся/закрывающейся)

Через `Ctrl` + `M`:

![Переход к соответствующей скобке](img/jump-to-bracket.png)

## Как посмотреть превью markdown файла

Превью появляется после комбинации клавиш `Ctrl` + `Shift` + `M`:

![Превью markdown файла](img/markdown-preview.png)

## Как открыть несколько проектов (папок)

![Добавление новой папки](img/add-project-folder_01.png)

И у вас будет открыто несколько папок:

![Несколько открытых папок](img/add-project-folder_02.png)

## Как полностью удалить Atom

Вначале удаляем как обычное приложение через `Программы и компоненты` в панели управления.

А потом в папке `C:\Users\[Пользователь]` удаляем папку `.atom`:

![Папка .atom](img/atom-folder_01.png)

Также возможно придется полазить в реестре и поудалять упоминания об Atom:

![Поиск в реестре](img/regedit_01.png)

![Ввод поискового запроса](img/regedit_02.png)

И какие-то файлы могут остаться в папке ``C:\Users\[Пользователь]\AppData\Local`в папке`atom`:

![Папка atom](img/atom-folder_02.png)

## Набор горячих клавиш

Клавиатурные сокращения можно посмотреть тут:

![Клавиатурные сокращения](img/keybindings.png)

Ниже представлен список горячих клавиш, которые я использую.

`Ctrl` + `S` — сохранить файл.

`Ctrl` + `Shift` + `P` — открыть консоль Atom.

`Ctrl` + `Alt` + `C` — выбор цвета с помощью плагина color-picker.

`Ctrl` + `Shift` + `T` — открытие последней закрытой вкладки.

`Ctrl` + `Alt` + `O` — добавляет список функций в файле для быстрого перехода между ними в плагине symbols-tree-view.

`F5` — сортировка.

`Ctrl` + `P` — поиск файла в проекте по имени.

`Ctrl` + `F` — поиск и замена.

`Shift` + `Ctrl` + `F` — поиск по всем файлам проекта.

`Ctrl` + `Shift` + `D` — продублировать строку.

`Ctrl` + `/` — закомментировать строки.

`Ctrl` + `J` — объединить строки в одну.

`Ctrl` + `Alt` + `F2` — поставить метку около строчки.

`F2` — перемещение между метками строк.

`Ctrl` + `Space` — вызов автодополнения.

`Ctrl` + `K` + `U` — все буквы заглавными.

`Ctrl` + `K` + `L` — все буквы маленькими.

`Ctrl` + `M` — перейти к соответствующей скобке (открывающейся/закрывающейся).

`Ctrl` + `Shift` + `M` — превью markdown файла.

`Ctrl` + `Shift` + `:` — вызов подсказок, как исправить слово.

`Ctrl` + `Alt` + `V` — превью SVG файлов.

`Ctrl` + `Alt` + `B` — расставляем отступы в коде.

`Ctrl` + `Shift` + `I` — нужно нажать два раза, чтобы вызвать Developer Tools.

`Ctrl` + `Alt` + `O` — открытие файлов, папок, их создание с помощью плагина advanced-open-file.

`Ctrl` + `Alt` + `Down` — можно редактировать несколько строк одновременно.

`Alt` + `[` и `Alt` + `]` — переключение между вкладками с помощью пакета tab-switcher.
