
# Домашнее задание по теме: Простейшие линейные алгоритмы в C#

## Задания

### 1. Умножение трех чисел
Напишите программу, которая запрашивает у пользователя три числа и выводит их произведение.

Пример:
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

        Console.WriteLine("Введите третье число:");
        int num3 = int.Parse(Console.ReadLine());

        int product = num1 * num2 * num3;
        Console.WriteLine("Произведение: " + product);
    }
}
```

### 2. Конвертер сантиметров в метры
Напишите программу, которая запрашивает у пользователя длину в сантиметрах и переводит её в метры.

Пример:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите длину в сантиметрах:");
        double centimeters = double.Parse(Console.ReadLine());

        double meters = centimeters / 100;
        Console.WriteLine("Длина в метрах: " + meters);
    }
}
```

### 3. Расчет объема цилиндра
Напишите программу, которая запрашивает у пользователя радиус и высоту цилиндра, а затем выводит его объем. Используйте формулу: V = π * r^2 * h, где π = 3.14159.

Пример:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите радиус цилиндра:");
        double radius = double.Parse(Console.ReadLine());

        Console.WriteLine("Введите высоту цилиндра:");
        double height = double.Parse(Console.ReadLine());

        double volume = 3.14159 * radius * radius * height;
        Console.WriteLine("Объем цилиндра: " + volume);
    }
}
```

### 4. Конвертер минут в часы и минуты
Напишите программу, которая запрашивает у пользователя количество минут и выводит, сколько это часов и минут.

Пример:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите количество минут:");
        int totalMinutes = int.Parse(Console.ReadLine());

        int hours = totalMinutes / 60;
        int minutes = totalMinutes % 60;

        Console.WriteLine("Это " + hours + " часов и " + minutes + " минут.");
    }
}
```

### 5. Расчет средней скорости
Напишите программу, которая запрашивает у пользователя расстояние (в километрах) и время (в часах), затем выводит среднюю скорость.

Пример:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите расстояние в километрах:");
        double distance = double.Parse(Console.ReadLine());

        Console.WriteLine("Введите время в часах:");
        double time = double.Parse(Console.ReadLine());

        double speed = distance / time;
        Console.WriteLine("Средняя скорость: " + speed + " км/ч");
    }
}
```


