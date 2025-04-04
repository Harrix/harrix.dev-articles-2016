---
date: 2016-03-26
categories:
  - it
  - programming
tags:
  - Qt
  - Базы данных
update: 2019-08-07
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/qt-webengine/qt-webengine.md
permalink: https://harrix.dev/ru/articles/2016/qt-webengine/
lang: ru
---

# Qt WebEngine в Qt Widgets приложении для просмотра веб-страниц

![Featured image](featured-image.svg)

В статье рассказывается, как в подключить Qt WebEngine в Qt Widgets приложении в виде примера открытия сайтов с помощью данного компонента.

В версии Qt 5.6.0 выпилили `QWebKit`. Вместо него теперь `Qt WebEngine`. Так что придется теперь работать с ним. Обратите внимание, что новый компонент пока работает только для версии Qt под компилятором Visual Studio.

В `Design` режиме в Qt 5.6.0 еще нет данного компонента (возможно потом добавят). Поэтому нужно будет либо его нужно будет вручную добавить в файл формы, либо «скоммуниздить» из какого-нибудь примера. Пойдем вторым способом.

Перейдем в режим примеров:

![Раздел примеров](img/get-component_01.png)

_Рисунок 1 — Раздел примеров_

Например, нужный нам компонент есть в приложении `WebEngine Markdown Editor Example`. Щелкаем по нему:

![Проект WebEngine Markdown Editor Example](img/get-component_02.png)

_Рисунок 2 — Проект WebEngine Markdown Editor Example_

![Первоначальная настройка проекта-примера](img/get-component_03.png)

_Рисунок 3 — Первоначальная настройка проекта-примера_

Переходим на форму приложения:

![Переход на форму приложения](img/get-component_04.png)

_Рисунок 4 — Переход на форму приложения_

И там копируем компонент типа `QWebEngineView`:

![Копирование компонента](img/get-component_05.png)

_Рисунок 5 — Копирование компонента_

И вставляем его на форму нашего приложения:

![Компонент на форме](img/form_01.png)

_Рисунок 6 — Компонент на форме_

Я еще добавил на форму обычную кнопку и сделал компоновку по вертикали:

![Компоновка элементов по вертикали](img/form_02.png)

_Рисунок 7 — Компоновка элементов по вертикали_

![Итоговый вариант формы](img/form_03.png)

_Рисунок 8 — Итоговый вариант формы_

В `.pro` файле добавьте `webenginewidgets`:

![Редактирование PRO файла](img/pro.png)

_Рисунок 9 — Редактирование PRO файла_

В слоте клика кнопки напишите такой код, не забыв подключить `#include <QUrl>`:

```cpp
ui->preview->load(QUrl("http://www.google.com/"));
ui->preview->show();
```

![Код тестового примера](img/cpp.png)

_Рисунок 10 — Код тестового примера_

Теперь при старте программы и клике на кнопку (при наличии интернета) отобразится мой сайт:

![Результат выполнения программы](img/run.png)

_Рисунок 11 — Результат выполнения программы_

Кстати, если вам нужно открыть локальный файл, то вместо первой строчки в последнем коде может быть такая:

```cpp
ui->preview->load(QUrl::fromLocalFile("C:\\index.html"));
```
