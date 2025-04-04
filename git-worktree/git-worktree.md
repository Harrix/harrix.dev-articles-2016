---
date: 2016-08-01
categories:
  - it
  - programming
tags:
  - Git
  - GitHub
update: 2019-10-12
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/git-worktree/git-worktree.md
permalink: https://harrix.dev/ru/articles/2016/git-worktree/
lang: ru
---

# Вынесение проекта в момент конкретного коммита в отдельную папку

![Featured image](featured-image.svg)

Всем Git хорошо, но некоторые вещи, которые мне бы хотелось там увидеть, не всегда очевидны. Вот ведете вы какой-то проект, делаете коммиты. И в какой-то момент, вам нужно посмотреть на проект в момент какого-то коммита. Желательно, чтобы вы смогли выгрузить данную прошлую версию проекта куда-нибудь в другое место, а не в основную ветку.

Оказывается, что есть команда, которая именно это и делает:

```shell
git worktree add ../[NewFolder] [commit]
```

Как я ею пользуюсь.

Открываю консоль нужного репозитория в `GitHub Desktop`:

![Вызов консоли](img/command-prompt.png)

_Рисунок 1 — Вызов консоли_

После этого нахожу в истории нужный коммит и копирую его SHA через нажатие правой кнопки по коммиту в истории:

![Копирование SHA](img/sha.png)

_Рисунок 2 — Копирование SHA_

Создаю в папке, где все репозитории находятся, папку с именем `[Имя репозитория]_commit`:

![Папки репозитория](img/folder.png)

_Рисунок 3 — Папки репозитория_

И в консоли вызываю подобную команду:

```shell
git worktree add ../Harrix-Rainmeter-Skin_commit 612d5735213443ed6f488e461ab5b4fd9f94ac75
```

![Выполнение команды в консоли](img/console.png)

_Рисунок 4 — Выполнение команды в консоли_

Всё. Теперь в папке `Harrix-Rainmeter-Skin_commit` находится образ проекта в момент конкретного коммита. При этом основная папка с проектом нетронута. Очень удобно.

Когда мне этот кусок будет не нужен, то папку можно очистить, а в папке `.git` основной ветки удалить папку `worktrees`.
