# Практические задания: Конструкция `switch-case`

## Задача 1: Калькулятор дней в месяце
Напишите программу, которая принимает номер месяца и выводит количество дней в этом месяце.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите номер месяца (1–12):");
        if (int.TryParse(Console.ReadLine(), out int month))
        {
            switch (month)
            {
                case 1:
                case 3:
                case 5:
                case 7:
                case 8:
                case 10:
                case 12:
                    Console.WriteLine("31 день.");
                    break;
                case 4:
                case 6:
                case 9:
                case 11:
                    Console.WriteLine("30 дней.");
                    break;
                case 2:
                    Console.WriteLine("28 или 29 дней.");
                    break;
                default:
                    Console.WriteLine("Неверный номер месяца.");
                    break;
            }
        }
        else
        {
            Console.WriteLine("Введено некорректное значение.");
        }
    }
}
```

---

## Задача 2: Проверка чётности числа
Напишите программу, которая запрашивает у пользователя число и определяет, является ли оно чётным.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите число:");
        if (int.TryParse(Console.ReadLine(), out int number))
        {
            switch (number % 2)
            {
                case 0:
                    Console.WriteLine("Число чётное.");
                    break;
                default:
                    Console.WriteLine("Число нечётное.");
                    break;
            }
        }
        else
        {
            Console.WriteLine("Введено некорректное значение.");
        }
    }
}
```

---

## Задача 3: Определение типа треугольника
Напишите программу, которая запрашивает у пользователя три стороны треугольника и определяет его тип: равносторонний, равнобедренный или разносторонний.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите три стороны треугольника:");
        if (double.TryParse(Console.ReadLine(), out double a) &&
            double.TryParse(Console.ReadLine(), out double b) &&
            double.TryParse(Console.ReadLine(), out double c))
        {
            switch ((a == b, b == c, a == c))
            {
                case (true, true, true):
                    Console.WriteLine("Треугольник равносторонний.");
                    break;
                case (true, false, false):
                case (false, true, false):
                case (false, false, true):
                    Console.WriteLine("Треугольник равнобедренный.");
                    break;
                default:
                    Console.WriteLine("Треугольник разносторонний.");
                    break;
            }
        }
        else
        {
            Console.WriteLine("Введены некорректные значения.");
        }
    }
}
```

---

## Задача 4: Классификация оценки
Напишите программу, которая запрашивает у пользователя оценку (число от 1 до 5) и выводит её текстовое описание.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите оценку (1–5):");
        if (int.TryParse(Console.ReadLine(), out int grade))
        {
            switch (grade)
            {
                case 1:
                    Console.WriteLine("Очень плохо.");
                    break;
                case 2:
                    Console.WriteLine("Плохо.");
                    break;
                case 3:
                    Console.WriteLine("Удовлетворительно.");
                    break;
                case 4:
                    Console.WriteLine("Хорошо.");
                    break;
                case 5:
                    Console.WriteLine("Отлично.");
                    break;
                default:
                    Console.WriteLine("Некорректная оценка.");
                    break;
            }
        }
        else
        {
            Console.WriteLine("Введено некорректное значение.");
        }
    }
}
```

---

## Задача 5: Простая викторина
Напишите программу, которая задаёт пользователю вопрос с выбором ответа и обрабатывает его.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Какой язык программирования используется для разработки под .NET?");
        Console.WriteLine("1. Python");
        Console.WriteLine("2. C#");
        Console.WriteLine("3. Java");
        Console.WriteLine("4. Ruby");
        
        if (int.TryParse(Console.ReadLine(), out int choice))
        {
            switch (choice)
            {
                case 1:
                    Console.WriteLine("Неверно! Это Python.");
                    break;
                case 2:
                    Console.WriteLine("Верно! Это C#.");
                    break;
                case 3:
                    Console.WriteLine("Неверно! Это Java.");
                    break;
                case 4:
                    Console.WriteLine("Неверно! Это Ruby.");
                    break;
                default:
                    Console.WriteLine("Некорректный выбор.");
                    break;
            }
        }
        else
        {
            Console.WriteLine("Введено некорректное значение.");
        }
    }
}
```
