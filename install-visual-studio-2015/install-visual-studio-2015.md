---
date: 2016-02-14
categories: [it, program]
tags: [Установка, Visual Studio, C++]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
---

# Установка Visual Studio 2015 Community

В статье приведена инструкция по установке бесплатной версии Visual Studio 2015 Community на Windows 10 для программирования на C++.

**Внимание!** Вышла Visual Studio 2019. [Читайте](https://github.com/Harrix/harrix.dev-blog-2021/blob/main/install-visual-studio-2019/install-visual-studio-2019.md) более новую статью.

Если вам нужна именно версия 2015 года, то читайте эту статью: [Скачивание старых версий Visual Studio](https://github.com/Harrix/harrix.dev-blog-2018/blob/main/download-old-versions-vs/download-old-versions-vs.md).

Далее идет старая инструкция, как устанавливать Visual Studio 2015 после скачивания инсталлятора.

## Установка

Запускаем скаченный файл:

![Запуск файла](img/install_01.png)

Windows начнет автоматически что-то скачивать и это нормально:

![Автоматическое скачивание](img/install_02.png)

И после этого будет предложено запустить установку Visual Studio. Жмем `Запустить`:

![Запуск установки](img/install_03.png)

После этого некоторое время будет висеть окно с логотипом студии:

![Начальное окно установки](img/install_04.png)

Параметры установки выбираем по умолчанию:

![Параметры по умолчанию](img/install_05.png)

`Внимание!` Если вы разбираетесь в теме, то можно выбрать выборочную установку и сократить себе шаги, описанные ниже. О параметрах выборочной установки под спойлером.

---

**Выборочная установка** <!-- !details -->

![Выбор типа установки](img/custom-install_01.png)

![Выбор выборочной установки](img/custom-install_02.png)

![Выбор настроек](img/custom-install_03.png)

![Выбор настроек](img/custom-install_04.png)

![Процесс установки](img/custom-install_05.png)

---

И установка началась:

![Процесс установки](img/install_06.png)

Скачиваться будет долго.

После завершения установки перезагрузите компьютер.

После этого запускаете Visual Studio. Но не найдетесь, что на этом всё.

При запуске вас попросят зайти под учеткой Microsoft. Если у вас её нет, то создайте на их сайте <https://www.microsoft.com/ru-ru/>.

Введите потом в Visual Studio электронную почту, на которую заведена учетка Microsoft:

![Ввод email](img/sign-in_01.png)

Можно потом выбрать чья это учетка: ваша личная или вы работаете где-то:

![Выбор типа учетки](img/sign-in_02.png)

Вводите данные своей учетки:

![Ввод пароля](img/sign-in_03.png)

Может вылететь такая ошибка — ничего страшного:

![Ошибка](img/sign-in_04.png)

И напоследок при первом запуске студии вас попросят выбрать тему оформления:

![Выбор темы](img/design-theme.png)

И Visual Studio запустилась! Но, к сожалению, еще не всё. Если вы создадите пустой проект на C++, то увидите, что пакеты для приложений на C++ не установились по умолчанию:

![Новый проект](img/new-project_01.png)

![Отсутствие типов проектов](img/new-project_02.png)

Поэтому жмем на `Install Visual C++ Tools for Windows Desktop`:

В появившемся окне жмем `Установить`:

![Начальное окно установки](img/install-cpp-tools_01.png)

![Начало установки](img/install-cpp-tools_02.png)

![Выбор компонентов для установки](img/install-cpp-tools_03.png)

![Запуск установки](img/install-cpp-tools_04.png)

Установка тоже может длиться долго:

![Конец установки](img/install-cpp-tools_05.png)

Теперь при создании проекта вы увидите привычные проекты для C++.

Можете попробовать создать простое консольное приложение по уроку:

[Создание консольного приложения сложения двух чисел Win32 в Visual Studio 2013](https://github.com/Harrix/harrix.dev-blog-2015/blob/main/add-2-num-vs-2013-console/add-2-num-vs-2013-console.md).
