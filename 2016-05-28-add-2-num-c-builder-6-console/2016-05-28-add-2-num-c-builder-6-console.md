---
categories: [it, programming]
tags: [C++, C++ Builder, Borland, Сложение двух чисел]
---

# Сложение двух чисел в C++ Builder 6 на C++ (консольное приложение)

В статье рассказывается как создать консольное приложение сложения двух чисел в древнем и старом C++ Builder 6.

## Создание нового приложения

![Выбор создание нестандартного проекта](img/new-project_01.png)

![Вызов Console Wizard](img/new-project_02.png)

![Выбор параметров проекта](img/new-project_03.png)

![Подтверждение сохранения изменений предыдущего проекта](img/new-project_04.png)

В итоге, появится вот такое окно:

![Созданный проект](img/new-project_05.png)

Сохраните всё:

![Сохранение файла исходного кода](img/new-project_06.png)

![Сохранения файла проекта](img/new-project_07.png)

## Написание кода

Пропишите выше функции `main`:

```cpp
#include <iostream>

using namespace std;
```

А в самой функции `main` пропишите стандартный код:

```cpp
int a,b,c;

cout << "Input first number:"<<endl;
cin >> a;
cout << "Input second number:"<<endl;
cin >> b;

c = a + b;

cout << a << " + " << b << " = " << c << endl;

system("pause");
return 0;
```

Общий код будет выглядеть так:

```cpp
//---------------------------------------------------------------------------

#pragma hdrstop

#include <iostream>

using namespace std;

//---------------------------------------------------------------------------

#pragma argsused
int main(int argc, char* argv[])
{
        int a,b,c;

        cout << "Input first number:"<<endl;
        cin >> a;
        cout << "Input second number:"<<endl;
        cin >> b;

        c = a + b;

        cout << a << " + " << b << " = " << c << endl;

        system("pause");
        return 0;
}
//---------------------------------------------------------------------------
```

Сохраните всё и запустите:

![Запуск приложения](img/run.png)

![Результат выполнения программы](img/result.png)
