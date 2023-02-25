---
date: 2016-09-11
categories: [it, programming]
tags: [C++, Visual Studio, Работа с файлами, XML]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2016/blob/main/new-class-clr-vs-2015/new-class-clr-vs-2015.md
url: https://harrix.dev/ru/blog/2016/new-class-clr-vs-2015/
lang: ru
---

# Создание своего класса в CLR приложении в Visual Studio 2015 на C++/CLI

Учебный пример, для демонстрации создания своего класса, который бы взаимодействовал с формой приложения CLR приложении в Visual Studio 2015 на C++/CLI.

## Постановка задачи

Надо написать класс, который внутри себя имеет только одну строковую переменную. Класс получает из кнопки имя файла, а возвращает расширение файла в виде строки.

## Болванка приложения

Итак, создайте пустое приложение CLR с формой. Это можно сделать по [статье](https://github.com/Harrix/harrix.dev-blog-2016/blob/main/add-2-num-vs-2015-clr/add-2-num-vs-2015-clr.md) дойдя в ней до пункта «Интерфейс приложения».

## Интерфейс программы

Перетащите на форму кнопку и текстовое поле:

![Кнопка и текстовое поле](img/interface_01.png)

А также диалоговое окно открытия файла:

![Диалоговое окно открытия файла](img/interface_02.png)

## Создание своего класса

Правый клик по проекту, и создаем новый элемент:

![Вызов команды «Создать новый элемент»](img/new-class_01.png)

Создаем `ExampleClass.h`:

![Создание нового заголовочного файла](img/new-class_02.png)

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

Обратите внимание на тот факт, что нам перед словом `class` нужно еще написать `ref`, чтобы мы могли использовать тип `String^`.

Также я подключил `System::IO`, `System::Xml`. Просто данная статья будет использоваться теми, кому эти два пространства имен будут нужны. Но вы можете их удалить.

## Использование класса

Перейдем в файл `MyForm.h`:

![Переход на форму приложения](img/use-class_01.png)

Двойной клик по кнопке:

![Двойной клик по кнопке](img/use-class_02.png)

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

Не забываем вверху файла `MyForm.h` подключить наш файл класса:

```cpp
#include "ExampleClass.h"
```

![Подключение заголовочного файла класса](img/use-class_04.png)

## Запуск программы

Запускаем программу:

![Запуск приложения](img/run.png)

Нажимаем на кнопку:

![Клик на кнопку](img/result_01.png)

Выбираем файл:

![Выбор файла](img/result_02.png)

В текстовом поле видите расширение файла:

![Результат выполнения программы](img/result_03.png)
