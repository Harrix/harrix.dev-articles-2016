---
date: 2016-05-28
categories: [it, programming]
tags: [C++, C++ Builder, Сложение двух чисел]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2016/blob/main/add-2-num-c-builder-10/add-2-num-c-builder-10.md
url: https://harrix.dev/ru/blog/2016/add-2-num-c-builder-10/
lang: ru
---

# Сложение двух чисел в C++ Builder 10 Seattle на C++

![Featured image](featured-image.svg)

В статье рассказывается как создать приложение сложения двух чисел в C++ Builder 10 Seattle.

## Создание нового приложения

Переходим в `File` → `New` → `VCL Form Application - C++ Builder`:

![Создание нового проекта](img/new-project_01.png)

Появится вот такой вид:

![Созданный проект](img/new-project_02.png)

Сохраняем всё в папке новой:

![Сохранение проекта](img/new-project_03.png)

![Сохранение исходного кода проекта](img/new-project_04.png)

![Сохранение заголовочного файла проекта](img/new-project_05.png)

![Сохранение файла проекта](img/new-project_06.png)

## Заполняем форму

На форму кидаем два поля ввода:

![Компоненты TEdit](img/controls_01.png)

Кнопку:

![Компонент TButton](img/controls_02.png)

И поле для вывода многострочного текста:

![Компонент TMemo](img/controls_03.png)

В поле для вывода `Memo1` удалим первоначальное содержимое:

![Свойство Lines компонента Memo1](img/controls_04.png)

![Содержимое свойство Lines](img/controls_05.png)

Также в поля ввода `Edit1` и `Edit2` введем первоначальное значение:

![Задание первоначального значения в полях ввода](img/controls_06.png)

## Написание кода

Теперь можно переходить к написанию кода.

Двойной клик по кнопке:

![Двойной клик по кнопке](img/click_01.png)

И видим это:

![Метод обработки клика по кнопке](img/click_02.png)

Вводим такой код:

```cpp
UnicodeString S1 = Edit1->Text;
UnicodeString S2 = Edit2->Text;

int a = S1.ToInt();
int b = S2.ToInt();

int c = a + b;

Memo1->Lines->Add(UnicodeString(a) + " + " + UnicodeString(b) + " = " + UnicodeString(c));
```

![Код метода обработки клика кнопки](img/click_03.png)

Теперь сохраняем всё и запускаем приложение:

![Запуск приложения](img/run.png)

При нажатию на кнопку вы получите результат:

![Результат выполнения программы](img/result.png)
