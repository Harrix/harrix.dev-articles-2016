---
date: 2016-08-01
categories: [it, programming]
tags: [Git, GitHub]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/git-worktree-github-pages/git-worktree-github-pages.md
permalink: https://harrix.dev/ru/articles/2016/git-worktree-github-pages/
lang: ru
---

# Совмещаем gh-pages с git-worktree

![Featured image](featured-image.svg)

GitHub pages — отличный способ публикации сайтов о ваших проектах на GitHub. Для этого нужно создать ветку в репозитории с названием gh-pages, где нужно разместить нужные HTML файлы. Однако это означает, что придется постоянно переключатся между двумя ветками, чтобы вносить изменения в репозиторий и на сайт о данном репозитории. Но на помощь приходит сравнительно новая команда worktree.

## Создание новой ветки

Покажу на примере одного из своего репозитории <https://github.com/Harrix/Standard-Genetic-Algorithm>.

На самом деле, не очень люблю консоль и предпочитаю GUI клиенты. Однако с командой `worktree` программа `GitHub Desktop` нормально работать не умеет, поэтому будем работать в консоли `Git Shell`:

![Консоль Git Shell](img/git-shell.png)

_Рисунок 1 — Консоль Git Shell_

Переходим в папку нашего проекта:

```powershell
cd RepositoryName
```

У меня это будет:

```powershell
cd Standard-Genetic-Algorithm
```

![Переход в папку репозитория](img/console_01.png)

_Рисунок 2 — Переход в папку репозитория_

Создаем новую ветку с именем `gh-pages` (именно с таким именем, если хотим её публиковать на GitHub Pages):

```powershell
git checkout -b gh-pages
```

![Создание новой ветки](img/console_02.png)

_Рисунок 3 — Создание новой ветки_

Отправляем ветку на сервер:

```powershell
git push -u origin gh-pages
```

![Публикация ветки на сервере](img/console_03.png)

_Рисунок 4 — Публикация ветки на сервере_

Теперь в репозитории две ветки:

![Две ветки на сервере](img/github.png)

_Рисунок 5 — Две ветки на сервере_

## Наполнение сайта

Удаляем всё из рабочей папки:

![Содержимое папки репозитория](img/folder_01.png)

_Рисунок 6 — Содержимое папки репозитория_

Вставляем HTML страницу с каким-нибудь наполнением:

![HTML файл с CSS стилями](img/folder_02.png)

_Рисунок 7 — HTML файл с CSS стилями_

Теперь командами делаем коммит и отправляем его на сервер:

```powershell
git add .
git commit -m "HTML Template"
git push
```

![Создание нового коммита](img/console_04.png)

_Рисунок 8 — Создание нового коммита_

Теперь по адресу `https://harrix.github.io/Standard-Genetic-Algorithm/` (`harrix` — мой логин на GitHub, а `Standard-Genetic-Algorithm` — название репозитория) появится сайт репозитория:

![Созданный сайт](img/site.png)

_Рисунок 9 — Созданный сайт_

Да, сейчас данный «сайт» не будет работать, так как он создавался только для написания статьи.

## Создание worktree

Всё хорошо, однако придется постоянно переключатся между ветками, чтобы работать то с сайтом, то с самим проектом. Было бы здорово, если бы на компе было сразу две папки с содержимым сайта и самим проектом. Что и сделаем.

В основной папке репозитория (у меня это `C:\Dropbox\GitHub\Standard-Genetic-Algorithm`) будем хранить ветку `master`. А в другой папке будем хранить ветку `gh-pages`.

Создадим эту новую папку уровнем выше. Предлагаю её называть так: `[Имя репозитория]_[Имя ветки]`.

Разумеется, что папку можно создать и обычным способом в Проводнике. Но раз мы в консоли, то там и сделаем, и вернемся обратно в нашу старую папку:

```powershell
cd ..
mkdir Standard-Genetic-Algorithm_gh-pages
cd Standard-Genetic-Algorithm
```

![Создание новой папки](img/folder_03.png)

_Рисунок 10 — Создание новой папки_

Переключимся на ветку `master`:

```powershell
git checkout master
```

![Переключение на другую ветку](img/console_05.png)

_Рисунок 11 — Переключение на другую ветку_

Теперь в новую папку отправим ветку `gh-pages`:

```powershell
git worktree add ../Standard-Genetic-Algorithm_gh-pages gh-pages
```

![Выполнение команды worktree](img/console_06.png)

_Рисунок 12 — Выполнение команды worktree_

Теперь в папке `Standard-Genetic-Algorithm_gh-pages` у нас находится содержимое ветки `gh-pages`:

![Содержимое папки Standard-Genetic-Algorithm_gh-pages](img/folder_04.png)

_Рисунок 13 — Содержимое папки Standard-Genetic-Algorithm_gh-pages_

А в папке `Standard-Genetic-Algorithm` находится основная ветка `master`:

![Содержимое папки Standard-Genetic-Algorithm](img/folder_05.png)

_Рисунок 14 — Содержимое папки Standard-Genetic-Algorithm_

## Как делать коммиты

Теперь мы можем одновременно работать с двумя папками, и не нужно будет переключаться постоянно между ветками. Однако вначале я помучился с понимаем того, а как делать коммиты в этих двух ветках.

В основной ветке всё просто:

```powershell
git add .
git commit -m "BlaBla"
git push
```

А вот изменения в ветке gh-pages не видятся, и переключение командой `git checkout gh-pages` не работает.

Всё просто. Нужно просто перейти в папку, где у нас находится эта ветка и там обычным способом создавать коммит:

```powershell
cd ../Standard-Genetic-Algorithm_gh-pages
git add .
git commit -m "BlaBlaBla"
git push
```

![Создание коммитов в соседней ветке](img/console_07.png)

_Рисунок 15 — Создание коммитов в соседней ветке_

А потом, если нужно, опять переходим в папку основной ветки:

```powershell
cd ../Standard-Genetic-Algorithm
```

## Дополнительно

Командой `git worktree list` можно узнать список веток, выделенных под разные папки:

![Список веток в worktree](img/console_08.png)

_Рисунок 16 — Список веток в worktree_

В GitHub Desktop в GUI режиме можно будет коммиты делать только для основной ветки. Коммиты для веток, вынесенных командой `worktree` придется делать в консоли.
