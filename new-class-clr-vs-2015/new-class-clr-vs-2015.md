---
date: 2016-09-11
categories:
  - it
  - programming
tags:
  - C++
  - Visual Studio
  - Работа с файлами
  - XML
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/new-class-clr-vs-2015/new-class-clr-vs-2015.md
permalink: https://harrix.dev/ru/articles/2016/new-class-clr-vs-2015/
lang: ru
---

# Создание своего класса в CLR приложении в Visual Studio 2015 на C++/CLI

![Featured image](featured-image.svg)

Учебный пример, для демонстрации создания своего класса, который бы взаимодействовал с формой приложения CLR приложении в Visual Studio 2015 на C++/CLI.

<details>
<summary>📖 Содержание ⬇️</summary>

## Содержание

- [Постановка задачи](#постановка-задачи)
- [Болванка приложения](#болванка-приложения)
- [Интерфейс программы](#интерфейс-программы)
- [Создание своего класса](#создание-своего-класса)
- [Использование класса](#использование-класса)
- [Запуск программы](#запуск-программы)

</details>

## Постановка задачи

Надо написать класс, который внутри себя имеет только одну строковую переменную. Класс получает из кнопки имя файла, а возвращает расширение файла в виде строки.

## Болванка приложения

Итак, создайте пустое приложение CLR с формой. Это можно сделать по [статье](https://github.com/Harrix/harrix.dev-articles-2016/blob/main/add-2-num-vs-2015-clr/add-2-num-vs-2015-clr.md) | [↗️](https://harrix.dev/ru/articles/2016/add-2-num-vs-2015-clr/) дойдя в ней до пункта «Интерфейс приложения».

## Интерфейс программы

Перетащите на форму кнопку и текстовое поле:

![Кнопка и текстовое поле](img/interface_01.png)

_Рисунок 1 — Кнопка и текстовое поле_

А также диалоговое окно открытия файла:

![Диалоговое окно открытия файла](img/interface_02.png)

_Рисунок 2 — Диалоговое окно открытия файла_

## Создание своего класса

Правый клик по проекту, и создаем новый элемент:

![Вызов команды «Создать новый элемент»](img/new-class_01.png)

_Рисунок 3 — Вызов команды «Создать новый элемент»_

Создаем `ExampleClass.h`:

![Создание нового заголовочного файла](img/new-class_02.png)

_Рисунок 4 — Создание нового заголовочного файла_

И в новом файле добавляем такой код:

```cpp
using namespace System;
using namespace System::IO;
using namespace System::Xml;

ref class ExampleClass {
public:
  ExampleClass();
  ExampleClass(String^ fileName);
  void setFileName(String^ fileName);
  String^ getFileExtension();
private:
  String^ fileName;
};
ExampleClass::ExampleClass() {
  fileName = "1.txt";
}
ExampleClass::ExampleClass(String^ fileName) {
  this->fileName = fileName;
}
void ExampleClass::setFileName(String^ fileName) {
  this->fileName = fileName;
}
String^ ExampleClass::getFileExtension() {
  int i = fileName->LastIndexOf(".");
  String^ Ext = fileName->Substring(i);
  return Ext;
}
```

![Код класса в редакторе](img/new-class_03.png)

_Рисунок 5 — Код класса в редакторе_

Обратите внимание на тот факт, что нам перед словом `class` нужно еще написать `ref`, чтобы мы могли использовать тип `String^`.

Также я подключил `System::IO`, `System::Xml`. Просто данная статья будет использоваться теми, кому эти два пространства имен будут нужны. Но вы можете их удалить.

## Использование класса

Перейдем в файл `MyForm.h`:

![Переход на форму приложения](img/use-class_01.png)

_Рисунок 6 — Переход на форму приложения_

Двойной клик по кнопке:

![Двойной клик по кнопке](img/use-class_02.png)

_Рисунок 7 — Двойной клик по кнопке_

Там пишем код:

```cpp
if (openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)
{
  String^ fileName = openFileDialog1->FileName;
  ExampleClass a(fileName);

  String^ Ext = a.getFileExtension();
  textBox1->Text = Ext;
}
```

![Код обработки клика кнопки](img/use-class_03.png)

_Рисунок 8 — Код обработки клика кнопки_

Не забываем вверху файла `MyForm.h` подключить наш файл класса:

```cpp
#include "ExampleClass.h"
```

![Подключение заголовочного файла класса](img/use-class_04.png)

_Рисунок 9 — Подключение заголовочного файла класса_

## Запуск программы

Запускаем программу:

![Запуск приложения](img/run.png)

_Рисунок 10 — Запуск приложения_

Нажимаем на кнопку:

![Клик на кнопку](img/result_01.png)

_Рисунок 11 — Клик на кнопку_

Выбираем файл:

![Выбор файла](img/result_02.png)

_Рисунок 12 — Выбор файла_

В текстовом поле видите расширение файла:

![Результат выполнения программы](img/result_03.png)

_Рисунок 13 — Результат выполнения программы_
