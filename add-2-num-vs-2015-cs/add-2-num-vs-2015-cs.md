---
date: 2016-05-29
categories: [it, programming]
tags: [C#, Visual Studio, Сложение двух чисел]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2016/blob/main/add-2-num-vs-2015-cs/add-2-num-vs-2015-cs.md
url: https://harrix.dev/ru/blog/2016/add-2-num-vs-2015-cs/
lang: ru
---

# Сложение двух чисел в Visual Studio 2015 на C# (консольное приложение)

![Featured image](featured-image.svg)

В статье рассказывается как создать приложение сложения двух чисел в Visual Studio 2015 на C#.

## Создание проекта

![Создание нового проекта](img/new-project_01.png)

![Выбор типа нового проекта](img/new-project_02.png)

![Созданный проект](img/new-project_03.png)

## Интерфейс приложения

Перетащите два `textBox` на форму, в которые будем записывать наши числа:

![Поля ввода на форме приложения](img/controls_01.png)

Перетащите кнопку на форму:

![Кнопка на форме приложения](img/controls_02.png)

Перетащите третий `textBox` на форму, в которую мы будем выводить информацию. Также поменяем значение `Multiline` на `true`, чтобы можно было писать многострочные тексты:

![Параметр Multiline поля вывода](img/controls_03.png)

Теперь мы можем его растянуть вниз:

![Растянутый контрол](img/controls_04.png)

А в первых двух `textBox` поменяем начальное значение:

![Изменение начального текста в полях ввода](img/controls_05.png)

![Текущий вид формы](img/controls_06.png)

## Написание кода основной программы

Щелкнете по кнопке двойным кликом:

![Клик по кнопке](img/button_01.png)

Мы получили метод, в котором прописываем реакцию на клик нашей мыши:

![Метод обработки клика кнопки](img/button_02.png)

В фигурных скобках пропишем код нашей программы по считыванию двух чисел, их сложении и выводе результата:

```cs
int x, y, z;

// Считаем значение из первого lineEdit
string S1 = textBox1.Text;
// Переведем значение в число
x = Convert.ToInt32(S1);

// Считаем значение из второго lineEdit
string S2 = textBox2.Text;
// Переведем значение в число
y = Convert.ToInt32(S2);

// Посчитаем сумму
z = x + y;

// Выведем результат
textBox3.Text = z.ToString();
```

![Код метода обработки клика кнопки](img/code.png)

## Запуск программы

![Запуск программы](img/run.png)

Получаем наше приложение:

![Запущенная программа](img/result_01.png)

При вводе наших чисел получим вот это:

![Результат выполнения программы](img/result_02.png)
