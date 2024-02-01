---
date: 2016-08-27
categories: [it, programming]
tags: [Qt, Android]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/icon-qt-android/icon-qt-android.md
permalink: https://harrix.dev/ru/articles/2016/icon-qt-android/
lang: ru
attribution:
  - {
      author: Google Inc,
      author-site: "https://www.google.com/",
      license: CC BY 3.0,
      license-url: "https://creativecommons.org/licenses/by/3.0/",
      permalink: "https://commons.wikimedia.org/wiki/File:Android_robot.svg",
      permalink-date: 2019-10-13,
      name: Android robot.svg,
    }
  - {
      author: Qt Project,
      author-site: "https://www.qt.io",
      license: Public domain,
      license-url: "https://en.wikipedia.org/wiki/Public_domain",
      permalink: "https://commons.wikimedia.org/wiki/File:Qt_logo_2016.svg",
      permalink-date: 2019-01-26,
      name: Qt logo 2016.svg,
    }
---

# Как добавить иконку в приложение Qt под Android

![Featured image](featured-image.svg)

Чтобы добавить иконку в приложение, например, под Windows в Qt нужно просто добавить ICO файл и прописать его в PRO файле. C Android так не прокатит, так как там иконки надо прописывать через создание `AndroidManifest.xml`.

Итак, у нас есть какой-то Qt проект. Я буду рассматривать на примере приложения под Qt Quick Controls 2 на Qt 5.7, но для других случаев будет то же самое. Предполагаю, что вы уже [запускали приложение Qt под Android](https://github.com/Harrix/harrix.dev-articles-2018/blob/main/install-qt-advanced/install-qt-advanced.md)<!-- https://harrix.dev/ru/articles/2018/install-qt-advanced/ --> и у вас всё работает. Просто иконка стандартная, а не такая, какая вам нужно.

Проверяем, что приложение у нас будет компилироваться под `Release` режимом под ту платформу, что вам нужно:

![Переключение компиляции в режим Release](img/release.png)

_Рисунок 1 — Переключение компиляции в режим Release_

Заходите в раздел `Projects`:

![Раздел projects](img/projects.png)

_Рисунок 2 — Раздел projects_

Там заходите в детали разделе `Build Android APK`:

![Раздел Build Android APK](img/build-android-apk.png)

_Рисунок 3 — Раздел Build Android APK_

И там нажимаете `Create Templates`:

![Кнопка Create Templates](img/create-templates.png)

_Рисунок 4 — Кнопка Create Templates_

Можно выбрать папку, куда в проекте будут сохранятся все новые сгенерированные файлы:

![Выбор папки для сгенерированных файлов](img/folder.png)

_Рисунок 5 — Выбор папки для сгенерированных файлов_

В итоге, в проекте появился файл `AndroidManifest.xml` и другие файлы:

![Сгенерированные файлы](img/android-files.png)

_Рисунок 6 — Сгенерированные файлы_

И тут вы можете добавить свои иконки (какого размера иконки нужно добавлять можно посмотреть [тут](https://material.io/design/iconography/#grid-keyline-shapes)):

![Добавление иконок](img/icons.png)

_Рисунок 7 — Добавление иконок_

После этого сохраняете изменения, и можно запускать программу:

![Сохранение проекта](img/save.png)

_Рисунок 8 — Сохранение проекта_

![Запуск приложения](img/run.png)

_Рисунок 9 — Запуск приложения_

И в Android устройстве появится приложение с установленной иконкой:

![Установленное приложение в Android](img/result.png)

_Рисунок 10 — Установленное приложение в Android_

Кстати, в папке `android\res` можно вручную добавить папку `drawable-xhdpi`, куда поместить иконку большего размера:

![Папка с ресурсами](img/res-folder.png)

_Рисунок 11 — Папка с ресурсами_

К тому же вы можете в созданный AndroidManifest.xml вносить те изменения, которые вам нужны еще. Например, можно указать имя пакета, версию и так далее.

P.S. У меня почему-то нормально компилируется проект под Android и нормально на нем запускается наверно раза с третьего иногда. Имейте это ввиду.
