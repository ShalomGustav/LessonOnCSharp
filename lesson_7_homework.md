### Урок 7: Методы в C#

---

## Практические задания

### Задача 1: Расчёт площади треугольника по формуле Герона
Напишите программу, которая принимает длины трёх сторон треугольника и рассчитывает его площадь с использованием метода.

```csharp
using System;

class Program
{
    static double CalculateTriangleArea(double a, double b, double c)
    {
        double s = (a + b + c) / 2; // Полупериметр
        return Math.Sqrt(s * (s - a) * (s - b) * (s - c));
    }

    static void Main()
    {
        Console.WriteLine("Введите длины трёх сторон треугольника:");
        double a = double.Parse(Console.ReadLine());
        double b = double.Parse(Console.ReadLine());
        double c = double.Parse(Console.ReadLine());

        Console.WriteLine($"Площадь треугольника: {CalculateTriangleArea(a, b, c):F2}");
    }
}
```

---

### Задача 2: Проверка прямоугольного треугольника
Напишите программу, которая принимает длины трёх сторон треугольника и проверяет, является ли он прямоугольным, используя метод.

```csharp
using System;

class Program
{
    static bool IsRightTriangle(double a, double b, double c)
    {
        double max = Math.Max(a, Math.Max(b, c));
        if (max == a)
            return Math.Pow(a, 2) == Math.Pow(b, 2) + Math.Pow(c, 2);
        if (max == b)
            return Math.Pow(b, 2) == Math.Pow(a, 2) + Math.Pow(c, 2);
        return Math.Pow(c, 2) == Math.Pow(a, 2) + Math.Pow(b, 2);
    }

    static void Main()
    {
        Console.WriteLine("Введите длины трёх сторон треугольника:");
        double a = double.Parse(Console.ReadLine());
        double b = double.Parse(Console.ReadLine());
        double c = double.Parse(Console.ReadLine());

        Console.WriteLine(IsRightTriangle(a, b, c) ? "Треугольник прямоугольный" : "Треугольник не прямоугольный");
    }
}
```

---

### Задача 3: Решение квадратного уравнения
Напишите программу, которая решает квадратное уравнение вида ax^2 + bx + c = 0 и возвращает корни уравнения с использованием метода.

```csharp
using System;

class Program
{
    static string SolveQuadraticEquation(double a, double b, double c)
    {
        double discriminant = Math.Pow(b, 2) - 4 * a * c;
        if (discriminant > 0)
        {
            double root1 = (-b + Math.Sqrt(discriminant)) / (2 * a);
            double root2 = (-b - Math.Sqrt(discriminant)) / (2 * a);
            return $"Два корня: {root1:F2} и {root2:F2}";
        }
        else if (discriminant == 0)
        {
            double root = -b / (2 * a);
            return $"Один корень: {root:F2}";
        }
        else
        {
            return "Корней нет.";
        }
    }

    static void Main()
    {
        Console.WriteLine("Введите коэффициенты a, b и c:");
        double a = double.Parse(Console.ReadLine());
        double b = double.Parse(Console.ReadLine());
        double c = double.Parse(Console.ReadLine());

        Console.WriteLine(SolveQuadraticEquation(a, b, c));
    }
}
```

---

### Задача 4: Проверка существования треугольника
Напишите программу, которая принимает длины трёх сторон треугольника и проверяет, может ли существовать треугольник с такими сторонами.

```csharp
using System;

class Program
{
    static bool IsValidTriangle(double a, double b, double c)
    {
        return a + b > c && a + c > b && b + c > a;
    }

    static void Main()
    {
        Console.WriteLine("Введите длины трёх сторон треугольника:");
        double a = double.Parse(Console.ReadLine());
        double b = double.Parse(Console.ReadLine());
        double c = double.Parse(Console.ReadLine());

        Console.WriteLine(IsValidTriangle(a, b, c) ? "Треугольник существует." : "Треугольник не существует.");
    }
}
```

---

### Задача 5: Конвертация валют
Напишите программу, которая принимает сумму в одной валюте и конвертирует её в другую, используя фиксированный курс обмена.

```csharp
using System;

class Program
{
    static double ConvertCurrency(double amount, double rate)
    {
        return amount * rate;
    }

    static void Main()
    {
        Console.WriteLine("Введите сумму в исходной валюте:");
        double amount = double.Parse(Console.ReadLine());

        Console.WriteLine("Введите курс обмена:");
        double rate = double.Parse(Console.ReadLine());

        Console.WriteLine($"Результат конвертации: {ConvertCurrency(amount, rate):F2}");
    }
}
```

