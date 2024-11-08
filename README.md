
# Урок 1: Введение в программирование на C# - Простейшие линейные алгоритмы и синтаксис

## Теория

Линейные алгоритмы — это простейшие программы, которые выполняют операции последовательно, одна за другой, без условий или ветвлений. 
В C# для написания таких алгоритмов мы используем переменные, операторы и методы ввода/вывода.

### Основные компоненты и правила синтаксиса C#

1. **Переменные и типы данных** — Переменные используются для хранения данных (например, чисел или текста). В C# переменная объявляется с указанием типа данных. Например:
   ```csharp
   int number = 5;
   string text = "Пример";
   ```

2. **Типы данных**:
   - `int` — для целых чисел (например, 1, -10).
   - `double` — для чисел с плавающей точкой (например, 3.14).
   - `string` — для текста (например, "Привет").
   - `bool` — для логических значений (true или false).

3. **Операторы** — В C# доступны арифметические операторы: 
   - `+` для сложения,
   - `-` для вычитания,
   - `*` для умножения,
   - `/` для деления,
   - `%` для остатка от деления.

4. **Ввод и вывод данных** — Используем `Console.WriteLine()` для вывода данных и `Console.ReadLine()` для ввода.
   - `Console.WriteLine("Введите число:");` — выводит текст в консоль.
   - `int number = int.Parse(Console.ReadLine());` — считывает текст, введённый пользователем, и преобразует его в число.

5. **Ключевые слова и регистр** — В C# важно соблюдать регистр. Например, `int` и `Int` — это разные записи.
   - **Ключевые слова** — зарезервированные слова языка, такие как `class`, `static`, `void`, `int`, их нельзя использовать как имена переменных.
   - **Имена переменных** — должны начинаться с буквы и могут содержать буквы и цифры, но не могут содержать пробелы и специальные символы.

6. **Структура программы**:
   - **Классы** — в C# программа создается внутри класса. Имя класса принято писать с заглавной буквы.
   - **Методы** — методы содержат инструкции и вызываются для выполнения определённых задач. Метод `Main()` — это точка входа программы.
   - **Операторные скобки** — открывающие `{` и закрывающие `}` скобки группируют код в блоки. Каждый блок кода (например, метод) должен быть заключён в такие скобки.
     
>Данная часть теории будет описана позже

Пример первой программы:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Hello, World!");
    }
}
```

Эта программа выводит текст "Hello, World!" в консоль.

## Практические задания

### 1. Сложение двух чисел
Программа запрашивает у пользователя два числа и выводит их сумму.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите первое число:");
        int num1 = int.Parse(Console.ReadLine());

        Console.WriteLine("Введите второе число:");
        int num2 = int.Parse(Console.ReadLine());

        int sum = num1 + num2;
        Console.WriteLine("Сумма: " + sum);
    }
}
```

### 2. Перевод градусов Цельсия в Фаренгейты
Напишите программу, которая запрашивает у пользователя температуру в градусах Цельсия и переводит её в Фаренгейты по формуле: F = C * 9 / 5 + 32.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите температуру в градусах Цельсия:");
        double celsius = double.Parse(Console.ReadLine());

        double fahrenheit = celsius * 9 / 5 + 32;
        Console.WriteLine("Температура в градусах Фаренгейта: " + fahrenheit);
    }
}
```

### 3. Расчёт площади прямоугольника
Программа запрашивает у пользователя длину и ширину прямоугольника и выводит его площадь.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите длину прямоугольника:");
        double length = double.Parse(Console.ReadLine());

        Console.WriteLine("Введите ширину прямоугольника:");
        double width = double.Parse(Console.ReadLine());

        double area = length * width;
        Console.WriteLine("Площадь прямоугольника: " + area);
    }
}
```

### 4. Расчёт периметра прямоугольника
Напишите программу, которая запрашивает у пользователя длину и ширину прямоугольника и выводит его периметр.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите длину прямоугольника:");
        double length = double.Parse(Console.ReadLine());

        Console.WriteLine("Введите ширину прямоугольника:");
        double width = double.Parse(Console.ReadLine());

        double perimeter = 2 * (length + width);
        Console.WriteLine("Периметр прямоугольника: " + perimeter);
    }
}
```

### 5. Конвертер валют
Программа запрашивает у пользователя сумму в рублях и курс доллара и выводит эквивалент в долларах.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите сумму в рублях:");
        double rubles = double.Parse(Console.ReadLine());

        Console.WriteLine("Введите курс доллара:");
        double rate = double.Parse(Console.ReadLine());

        double dollars = rubles / rate;
        Console.WriteLine("Сумма в долларах: " + dollars);
    }
}
```

