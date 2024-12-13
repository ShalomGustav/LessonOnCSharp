# Урок 5. Практическая работа по темам 1-4.

## Задачи

Этот урок посвящен практической работе по темам прошлых занятий. Работы разбиты на три уровня сложности:

- `*` базовый уровень.
- `**` средний уровень.
- `***` высокий уровень.
  
---

1. `*` Вычисление суммы двух чисел.

Напишите программу, которая запрашивает два числа и выводит их сумму.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите первое число:");
        string inputA = Console.ReadLine();
        int a = int.Parse(inputA);

        Console.WriteLine("Введите второе число:");
        string inputB = Console.ReadLine();
        int b = int.Parse(inputB);

        Console.WriteLine($"Сумма: {a + b}");
    }
}
```

2. `*` Проверка на чётность.

Напишите программу, которая проверяет, является ли число чётным. Используя тернарную операцию.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите число:");
        string input = Console.ReadLine();
        int number = int.Parse(input);

        string result = number % 2 == 0 ? "Число чётное." : "Число нечётное.";
        Console.WriteLine(result);
    }
}
```

3. `*` Конвертация строки в число

Напишите программу, которая запрашивает строку и пытается преобразовать её в число, используя `int.TryParse`.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите строку:");
        string input = Console.ReadLine();

        if (int.TryParse(input, out int number))
        {
            Console.WriteLine($"Число: {number}");
        }
        else
        {
            Console.WriteLine("Некорректное значение.");
        }
    }
}
```

4. `**` Определение максимума трёх чисел.

Напишите программу, которая находит большее из трёх чисел. Обязательно используем `TryParse`.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите три числа через Enter:");
        string inputA = Console.ReadLine();
        string inputB = Console.ReadLine();
        string inputC = Console.ReadLine();

        if (int.TryParse(inputA, out int a) &&
            int.TryParse(inputB, out int b) &&
            int.TryParse(inputC, out int c))
        {
            if (a >= b && a >= c)
                Console.WriteLine($"Максимум: {a}");
            else if (b >= a && b >= c)
                Console.WriteLine($"Максимум: {b}");
            else
                Console.WriteLine($"Максимум: {c}");
        }
        else
        {
            Console.WriteLine("Некорректный ввод.");
        }
    }
}
```

5. `**` Проверка числа на принадлежность диапазону.

Напишите программу, которая проверяет, входит ли число в диапазон от 1 до 100. Используйте тернарную операцию.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите число:");
        string input = Console.ReadLine();

        if (int.TryParse(input, out int number))
        {
            bool inRange = number >= 1 && number <= 100;
            Console.WriteLine(inRange ? "Число входит в диапазон." : "Число не входит в диапазон.");
        }
        else
        {
            Console.WriteLine("Некорректный ввод.");
        }
    }
}
```

6. `**` Определение времени года.

Напишите программу, которая определяет время года по номеру месяца.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите номер месяца (1-12):");
        string input = Console.ReadLine();

        if (int.TryParse(input, out int month))
        {
            if (month == 12 || month == 1 || month == 2)
                Console.WriteLine("Зима");
            else if (month >= 3 && month <= 5)
                Console.WriteLine("Весна");
            else if (month >= 6 && month <= 8)
                Console.WriteLine("Лето");
            else if (month >= 9 && month <= 11)
                Console.WriteLine("Осень");
            else
                Console.WriteLine("Некорректный номер месяца.");
        }
        else
        {
            Console.WriteLine("Некорректный ввод.");
        }
    }
}
```

7. `***` Минимальный калькулятор.

Создайте программу, которая выполняет арифметические операции (+, -, *, /) с двумя числами, но добавьте обработку некорректных операторов.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите первое число:");
        string inputA = Console.ReadLine();
        if (double.TryParse(inputA, out double a))
        {
            Console.WriteLine("Введите второе число:");
            string inputB = Console.ReadLine();
            if (double.TryParse(inputB, out double b))
            {
                Console.WriteLine("Введите оператор (+, -, *, /):");
                string inputOp = Console.ReadLine();

                double result;
                if (inputOp == "+")
                    result = a + b;
                else if (inputOp == "-")
                    result = a - b;
                else if (inputOp == "*")
                    result = a * b;
                else if (inputOp == "/" && b != 0)
                    result = a / b;
                else
                {
                    Console.WriteLine("Некорректный оператор.");
                    return;
                }

                Console.WriteLine($"Результат: {result}");
            }
            else
            {
                Console.WriteLine("Некорректный ввод второго числа.");
            }
        }
        else
        {
            Console.WriteLine("Некорректный ввод первого числа.");
        }
    }
}
```

8. `***` Определение чётности и положительности числа.

Напишите программу, которая определяет, является ли число положительным и одновременно чётным. Используя тернарную операцию.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите число:");
        string input = Console.ReadLine();

        if (int.TryParse(input, out int number))
        {
            bool isPositiveAndEven = number > 0 && number % 2 == 0;
            string result = isPositiveAndEven ? "Число положительное и чётное." : "Условие не выполнено.";
            Console.WriteLine(result);
        }
        else
        {
            Console.WriteLine("Некорректный ввод.");
        }
    }
}
```

9. `***` Проверка кратности.

Напишите программу, которая проверяет, кратно ли число `X` числу `Y`.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите число X:");
        string inputX = Console.ReadLine();
        if (int.TryParse(inputX, out int x))
        {
            Console.WriteLine("Введите число Y:");
            string inputY = Console.ReadLine();
            if (int.TryParse(inputY, out int y) && y != 0)
            {
                bool isMultiple = x % y == 0;
                Console.WriteLine(isMultiple ? "X кратно Y." : "X не кратно Y.");
            }
            else
            {
                Console.WriteLine("Некорректный ввод или деление на ноль.");
            }
        }
        else
        {
            Console.WriteLine("Некорректный ввод X.");
        }
    }
}
```

