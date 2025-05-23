---
date: 2016-01-02
categories:
  - it
  - program
tags:
  - Notepad++
  - Текстовой редактор
  - Markdown
  - Подсветка синтаксиса
related-id: notepad-highlight
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/md-in-notepad-plus-plus/md-in-notepad-plus-plus.md
permalink: https://harrix.dev/ru/articles/2016/md-in-notepad-plus-plus/
lang: ru
attribution:
  - author: Dustin Curtis
    author-site: https://github.com/dcurtis
    license: CC0
    license-url: https://github.com/dcurtis/markdown-mark/blob/master/LICENSE
    permalink: https://commons.wikimedia.org/wiki/File:Markdown-mark.svg
    permalink-date: 2019-03-19
    name: Markdown-mark.svg
---

# Markdown в Notepad++

![Featured image](featured-image.svg)

Как открыть Markdown файл в Notepad++ с подсветкой синтаксиса?

Стили подсветки синтаксиса:

```xml
<UserLang name="Markdown" ext="md markdown" udlVersion="2.1">
    <Settings>
        <Global caseIgnored="no" allowFoldOfComments="no" foldCompact="no" forcePureLC="2" decimalSeparator="0" />
        <Prefix Keywords1="yes" Keywords2="yes" Keywords3="yes" Keywords4="yes" Keywords5="yes" Keywords6="no" Keywords7="no" Keywords8="no" />
    </Settings>
    <KeywordLists>
        <Keywords name="Comments">00# 01 02((EOL)) 03&lt;!-- 04--&gt;</Keywords>
        <Keywords name="Numbers, prefix1"></Keywords>
        <Keywords name="Numbers, prefix2"></Keywords>
        <Keywords name="Numbers, extras1"></Keywords>
        <Keywords name="Numbers, extras2"></Keywords>
        <Keywords name="Numbers, suffix1">.</Keywords>
        <Keywords name="Numbers, suffix2"></Keywords>
        <Keywords name="Numbers, range"></Keywords>
        <Keywords name="Operators1">@ &lt; &gt; \\ \` \* \_ \{ \} \[ \] \( \) \# \+ \- \. \!</Keywords>
        <Keywords name="Operators2">* - +</Keywords>
        <Keywords name="Folders in code1, open"></Keywords>
        <Keywords name="Folders in code1, middle"></Keywords>
        <Keywords name="Folders in code1, close"></Keywords>
        <Keywords name="Folders in code2, open"></Keywords>
        <Keywords name="Folders in code2, middle"></Keywords>
        <Keywords name="Folders in code2, close"></Keywords>
        <Keywords name="Folders in comment, open"></Keywords>
        <Keywords name="Folders in comment, middle"></Keywords>
        <Keywords name="Folders in comment, close"></Keywords>
        <Keywords name="Keywords1">http:// (http:// https:// (https:// mailto: (mailto: ftp:// (ftp:// ftps:// (ftps:// (/ /</Keywords>
        <Keywords name="Keywords2">==== ----</Keywords>
        <Keywords name="Keywords3">*** ___</Keywords>
        <Keywords name="Keywords4">** __</Keywords>
        <Keywords name="Keywords5">* _</Keywords>
        <Keywords name="Keywords6"></Keywords>
        <Keywords name="Keywords7"></Keywords>
        <Keywords name="Keywords8"></Keywords>
        <Keywords name="Delimiters">00![ 00[ 01\ 02] 02] 03` 04\ 05` 06*** 07\ 08*** 09** 10\ 11** 12 13 14 15 16 17 18 19 20 21 22 23</Keywords>
    </KeywordLists>
    <Styles>
        <WordsStyle name="DEFAULT" fgColor="333333" bgColor="FFFFFF" fontName="" fontStyle="0" nesting="0" />
        <WordsStyle name="COMMENTS" fgColor="808080" bgColor="FFFFFF" fontName="" fontStyle="2" nesting="0" />
        <WordsStyle name="LINE COMMENTS" fgColor="FF8000" bgColor="FFFFFF" fontName="" fontStyle="1" nesting="0" />
        <WordsStyle name="NUMBERS" fgColor="0080FF" bgColor="FFFFFF" fontName="" fontStyle="0" nesting="0" />
        <WordsStyle name="KEYWORDS1" fgColor="8000FF" bgColor="FFFFFF" fontName="" fontStyle="0" nesting="0" />
        <WordsStyle name="KEYWORDS2" fgColor="FF8000" bgColor="FFFFFF" fontName="" fontStyle="1" nesting="0" />
        <WordsStyle name="KEYWORDS3" fgColor="000080" bgColor="FFFFFF" fontName="" fontStyle="3" nesting="0" />
        <WordsStyle name="KEYWORDS4" fgColor="000080" bgColor="FFFFFF" fontName="" fontStyle="1" nesting="0" />
        <WordsStyle name="KEYWORDS5" fgColor="000080" bgColor="FFFFFF" fontName="" fontStyle="2" nesting="0" />
        <WordsStyle name="KEYWORDS6" fgColor="333333" bgColor="FFFFFF" fontName="" fontStyle="0" nesting="0" />
        <WordsStyle name="KEYWORDS7" fgColor="333333" bgColor="FFFFFF" fontName="" fontStyle="0" nesting="0" />
        <WordsStyle name="KEYWORDS8" fgColor="333333" bgColor="FFFFFF" fontName="" fontStyle="0" nesting="0" />
        <WordsStyle name="OPERATORS" fgColor="8080FF" bgColor="FFFFFF" fontName="" fontStyle="1" nesting="0" />
        <WordsStyle name="FOLDER IN CODE1" fgColor="333333" bgColor="FFFFFF" fontName="" fontStyle="0" nesting="0" />
        <WordsStyle name="FOLDER IN CODE2" fgColor="333333" bgColor="FFFFFF" fontName="" fontStyle="0" nesting="0" />
        <WordsStyle name="FOLDER IN COMMENT" fgColor="333333" bgColor="FFFFFF" fontName="" fontStyle="0" nesting="0" />
        <WordsStyle name="DELIMITERS1" fgColor="8000FF" bgColor="FFFFFF" fontName="" fontStyle="2" nesting="0" />
        <WordsStyle name="DELIMITERS2" fgColor="008000" bgColor="FFFFFF" fontName="" fontStyle="0" nesting="0" />
        <WordsStyle name="DELIMITERS3" fgColor="000080" bgColor="FFFFFF" fontName="" fontStyle="3" nesting="0" />
        <WordsStyle name="DELIMITERS4" fgColor="000080" bgColor="FFFFFF" fontName="" fontStyle="1" nesting="0" />
        <WordsStyle name="DELIMITERS5" fgColor="333333" bgColor="FFFFFF" fontName="" fontStyle="0" nesting="0" />
        <WordsStyle name="DELIMITERS6" fgColor="333333" bgColor="FFFFFF" fontName="" fontStyle="0" nesting="0" />
        <WordsStyle name="DELIMITERS7" fgColor="333333" bgColor="FFFFFF" fontName="" fontStyle="0" nesting="0" />
        <WordsStyle name="DELIMITERS8" fgColor="333333" bgColor="FFFFFF" fontName="" fontStyle="0" nesting="0" />
    </Styles>
</UserLang>
```

Идем сюда `%appdata%/Notepad++`.

Если там есть файл `userDefineLang.xml`, то копируем код XML из начала статьи в файл `userDefineLang.xml` перед последней строчкой:

```xml
</NotepadPlus>
```

Если там нет файла `userDefineLang.xml`, то создаем текстовой документ в этой папке и называем `userDefineLang.xml`. Открываем файл и добавляем в него строки:

```xml
<NotepadPlus>

</NotepadPlus>
```

И между тэгами `<NotepadPlus>` вставляем код XML из начала статьи.

Сохраняем, перезапускам Notepad++.

Теперь откройте какой-нибудь Markdown файл. Если подсветка синтаксиса не появилась, то идем `Синтаксис` → `Markdown`:

![Выбор подсветки синтаксиса](img/markdown_01.png)

_Рисунок 1 — Выбор подсветки синтаксиса_

Теперь все md файлы будут с подсветкой синтаксиса:

![Подсветка Markdown синтаксиса](img/markdown_02.png)

_Рисунок 2 — Подсветка Markdown синтаксиса_
