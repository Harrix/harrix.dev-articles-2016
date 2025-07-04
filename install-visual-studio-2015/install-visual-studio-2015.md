---
date: 2016-02-14
categories:
  - it
  - program
tags:
  - Установка
  - Visual Studio
  - C++
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/install-visual-studio-2015/install-visual-studio-2015.md
permalink: https://harrix.dev/ru/articles/2016/install-visual-studio-2015/
lang: ru
attribution:
  - author: Microsoft Corporation
    author-site: https://www.microsoft.com/
    license: Public domain
    license-url: https://en.wikipedia.org/wiki/Public_domain
    permalink: https://commons.wikimedia.org/wiki/File:Visual_Studio_2017_Logo.svg
    permalink-date: 2019-06-08
    name: Visual Studio 2017 Logo.svg
---

# Установка Visual Studio 2015 Community

![Featured image](featured-image.svg)

В статье приведена инструкция по установке бесплатной версии Visual Studio 2015 Community на Windows 10 для программирования на C++.

**Внимание!** Вышла Visual Studio 2019. [Читайте](https://github.com/Harrix/harrix.dev-articles-2021/blob/main/install-visual-studio-2019/install-visual-studio-2019.md) | [↗️](https://harrix.dev/ru/articles/2021/install-visual-studio-2019/) более новую статью.

Если вам нужна именно версия 2015 года, то читайте эту статью: [Скачивание старых версий Visual Studio](https://github.com/Harrix/harrix.dev-articles-2018/blob/main/download-old-versions-vs/download-old-versions-vs.md) | [↗️](https://harrix.dev/ru/articles/2018/download-old-versions-vs/).

Далее идет старая инструкция, как устанавливать Visual Studio 2015 после скачивания инсталлятора.

## Установка

Запускаем скаченный файл:

![Запуск файла](img/install_01.png)

_Рисунок 1 — Запуск файла_

Windows начнет автоматически что-то скачивать и это нормально:

![Автоматическое скачивание](img/install_02.png)

_Рисунок 2 — Автоматическое скачивание_

И после этого будет предложено запустить установку Visual Studio. Жмем `Запустить`:

![Запуск установки](img/install_03.png)

_Рисунок 3 — Запуск установки_

После этого некоторое время будет висеть окно с логотипом студии:

![Начальное окно установки](img/install_04.png)

_Рисунок 4 — Начальное окно установки_

Параметры установки выбираем по умолчанию:

![Параметры по умолчанию](img/install_05.png)

_Рисунок 5 — Параметры по умолчанию_

`Внимание!` Если вы разбираетесь в теме, то можно выбрать выборочную установку и сократить себе шаги, описанные ниже. О параметрах выборочной установки под спойлером.

<details>
<summary>Выборочная установка</summary>

![Выбор типа установки](img/custom-install_01.png)

_Рисунок 6 — Выбор типа установки_

![Выбор выборочной установки](img/custom-install_02.png)

_Рисунок 7 — Выбор выборочной установки_

![Выбор настроек](img/custom-install_03.png)

_Рисунок 8 — Выбор настроек_

![Выбор настроек](img/custom-install_04.png)

_Рисунок 9 — Выбор настроек_

![Процесс установки](img/custom-install_05.png)

_Рисунок 10 — Процесс установки_

</details>

И установка началась:

![Процесс установки](img/install_06.png)

_Рисунок 11 — Процесс установки_

Скачиваться будет долго.

После завершения установки перезагрузите компьютер.

После этого запускаете Visual Studio. Но не найдетесь, что на этом всё.

При запуске вас попросят зайти под учеткой Microsoft. Если у вас её нет, то создайте на их сайте <https://www.microsoft.com/ru-ru/>.

Введите потом в Visual Studio электронную почту, на которую заведена учетка Microsoft:

![Ввод email](img/sign-in_01.png)

_Рисунок 12 — Ввод email_

Можно потом выбрать чья это учетка: ваша личная или вы работаете где-то:

![Выбор типа учетки](img/sign-in_02.png)

_Рисунок 13 — Выбор типа учетки_

Вводите данные своей учетки:

![Ввод пароля](img/sign-in_03.png)

_Рисунок 14 — Ввод пароля_

Может вылететь такая ошибка — ничего страшного:

![Ошибка](img/sign-in_04.png)

_Рисунок 15 — Ошибка_

И напоследок при первом запуске студии вас попросят выбрать тему оформления:

![Выбор темы](img/design-theme.png)

_Рисунок 16 — Выбор темы_

И Visual Studio запустилась! Но, к сожалению, еще не всё. Если вы создадите пустой проект на C++, то увидите, что пакеты для приложений на C++ не установились по умолчанию:

![Новый проект](img/new-project_01.png)

_Рисунок 17 — Новый проект_

![Отсутствие типов проектов](img/new-project_02.png)

_Рисунок 18 — Отсутствие типов проектов_

Поэтому жмем на `Install Visual C++ Tools for Windows Desktop`:

В появившемся окне жмем `Установить`:

![Начальное окно установки](img/install-cpp-tools_01.png)

_Рисунок 19 — Начальное окно установки_

![Начало установки](img/install-cpp-tools_02.png)

_Рисунок 20 — Начало установки_

![Выбор компонентов для установки](img/install-cpp-tools_03.png)

_Рисунок 21 — Выбор компонентов для установки_

![Запуск установки](img/install-cpp-tools_04.png)

_Рисунок 22 — Запуск установки_

Установка тоже может длиться долго:

![Конец установки](img/install-cpp-tools_05.png)

_Рисунок 23 — Конец установки_

Теперь при создании проекта вы увидите привычные проекты для C++.

Можете попробовать создать простое консольное приложение по уроку:

[Создание консольного приложения сложения двух чисел Win32 в Visual Studio 2013](https://github.com/Harrix/harrix.dev-articles-2015/blob/main/add-2-num-vs-2013-console/add-2-num-vs-2013-console.md) | [↗️](https://harrix.dev/ru/articles/2015/add-2-num-vs-2013-console/).
