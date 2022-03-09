---
categories: [it, programming]
tags: [C++, Visual Studio]
---

# Создание класса с вектором экземпляров другого класса на C++/CLI

Не люблю C++/CLI. Но иногда приходится и с ним сталкиваться. В статье покажу пример класса с вектором экземпляров другого класса.

Данная статья построена на базе другой статьи [Создание своего класса в CLR приложении в Visual Studio 2015 на C++/CLI](https://github.com/Harrix/harrix.dev-blog-2016/blob/main/2016-09-11-new-class-clr-vs-2015/2016-09-11-new-class-clr-vs-2015.md). Так что вначале посмотрите её.

Там показан пример класса, который принимает в качестве параметра строку с именем файла и может возвращать расширение файла.

## ExampleClass.h

```cpp
#pragma once

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

В данном классе используется строка типа `String^`, поэтому придется использовать синтаксис не чистого C++, а `C++/CLI` (ref, gcnew и так далее).

Создадим новый класс, в котором будем хранить массив экземпляров класса `ExampleClass`. В качестве массива будем использовать обычный вектор. Проблемы возникнут с использованием векторов из стандартной библиотеки C++ `std::vector`, поэтому будем использовать `cliext::vector`.

Также обратите внимание на то, что в C++/CLI аналогом оператора `*` для указателей выступает `^`, а для ссылок `&` используется `%`.

Ниже приведен код простейшего класса, в котором есть нужный нам вектор.

## ClassWithVector.h

```cpp
#pragma once

#include "ExampleClass.h"
#include <cliext/vector>

using namespace System;
using namespace cliext;

ref class ClassWithVector {
public:
  vector<ExampleClass^>^ vectorExampleClass;

  ClassWithVector() {
    vectorExampleClass = gcnew vector<ExampleClass^>();
  }
};
```

В классе есть пока только конструктор класса и переменная класса `vector<ExampleClass^>^ vectorExampleClass`. Там появился забавный смайлик `^>^`. Почему? Сам вектор у нас объявляется как указатель, который в себе хранит указатели на экземпляры ExampleClass.

Теперь мы можем в форме приложения создать экземпляр класса `ClassWithVector` и закинуть в него элементы.

В форме подключите инклуды:

```cpp
#include "ExampleClass.h"
#include "ClassWithVector.h"
```

А, например, в обработчике клика кнопки пропишите следующее:

```cpp
ExampleClass ^temp = gcnew ExampleClass("file.txt");
ExampleClass ^temp2 = gcnew ExampleClass("info.xml");

ClassWithVector ^vec = gcnew ClassWithVector;
vec->vectorExampleClass->push_back(temp);
vec->vectorExampleClass->push_back(temp2);

textBox1->Text += vec->vectorExampleClass->at(0)->getFileExtension() + "\r\n";
textBox1->Text += vec->vectorExampleClass->at(1)->getFileExtension() + "\r\n";
```

При запуске приложения и нажатии на кнопку программа выдаст такой ответ:

```console
.txt
.xml
```

Теперь рассмотрим более сложный вариант использования класса:

```cpp
// Указатель на временный объект
ExampleClass ^temp;

// Экземпляр класса с вектором элементов внутри
ClassWithVector ^vec = gcnew ClassWithVector;

for (int i = 0; i < 5; i++) {
  // Создаем экземпляр временного объекта с названием файла вроде file.2ext
  String^ filename = "file." + i.ToString() + "ext";
  temp = gcnew ExampleClass (filename);

  // Закидываем экземпляр в вектор, который находится внутри vec
  vec->vectorExampleClass->push_back(temp);
}

// Сколько в векторе находится сейчас значений
int size = vec->vectorExampleClass->size();
// Вытаскиваем расширения всех файлов из вектора
for (int i = 0; i < size; i++) {
  textBox1->Text += vec->vectorExampleClass->at(i)->getFileExtension() + "\r\n";
}
```

Программа выдаст такое:

```console
.0ext
.1ext
.2ext
.3ext
.4ext
```

## С применением инкапсуляции

Теперь скроем наш вектор в `private`. Поэтому придется прописать нужные методы, которые обеспечат нас нужным функционалом:

```cpp
#pragma once

#include "ExampleClass.h"
#include <cliext/vector>

using namespace System;
using namespace cliext;

ref class ClassWithVector {
public:
  ClassWithVector(); // Конструктор
  int size(); // Возвращаем количество элементов вектора
  void add(ExampleClass^ temp); // Добавляем элемент в вектор
  ExampleClass^ getElement(int i); // Возвращаем элемент из вектора по номеру
private:
  vector<ExampleClass^>^ vectorExampleClass;
};
ClassWithVector::ClassWithVector() {
  vectorExampleClass = gcnew vector<ExampleClass^>();
}
int ClassWithVector::size() {
  return vectorExampleClass->size();
}
void ClassWithVector::add(ExampleClass^ temp) {
  vectorExampleClass->push_back(temp);
}
ExampleClass^ ClassWithVector::getElement(int i) {
  return vectorExampleClass->at(i);
}
```

И код кнопки тоже поменяется:

```cpp
// Указатель на временный объект
ExampleClass ^temp;

// Экземпляр класса с вектором элементов внутри
ClassWithVector ^vec = gcnew ClassWithVector;

for (int i = 0; i < 5; i++) {
  // Создаем экземпляр временного объекта с названием файла вроде file.2ext
  String^ filename = "file." + i.ToString() + "ext";
  temp = gcnew ExampleClass (filename);

  // Закидываем экземпляр в вектор, который находится внутри vec
  vec->add(temp);
}

// Сколько в векторе находится сейчас значений
int size = vec->size();
// Вытаскиваем расширения всех файлов из вектора
for (int i = 0; i < size; i++) {
  textBox1->Text += vec->getElement(i)->getFileExtension() + "\r\n";
}
```
