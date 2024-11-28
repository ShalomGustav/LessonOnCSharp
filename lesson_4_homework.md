
# Домашнее задание по теме: Условные конструкции: if, if-else, тернарная операция

## Задачи

### Задача 1: Проверка чётности числа

Программа должна запросить у пользователя число и вывести сообщение, является ли оно чётным.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите число:");
        if (int.TryParse(Console.ReadLine(), out int number))
        {
            Console.WriteLine(number % 2 == 0 ? "Число чётное." : "Число нечётное.");
        }
        else
        {
            Console.WriteLine("Введено некорректное значение.");
        }
    }
}
```

---

### Задача 2: Классификация дня недели

Программа должна запросить у пользователя номер дня недели (1–7) и вывести его название.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите номер дня недели (1–7):");
        if (int.TryParse(Console.ReadLine(), out int day))
        {
            if (day == 1) Console.WriteLine("Понедельник");
            else if (day == 2) Console.WriteLine("Вторник");
            else if (day == 3) Console.WriteLine("Среда");
            else if (day == 4) Console.WriteLine("Четверг");
            else if (day == 5) Console.WriteLine("Пятница");
            else if (day == 6) Console.WriteLine("Суббота");
            else if (day == 7) Console.WriteLine("Воскресенье");
            else Console.WriteLine("Неверный номер дня.");
        }
        else
        {
            Console.WriteLine("Введено некорректное значение.");
        }
    }
}
```

---

### Задача 3: Проверка диапазона

Программа должна запросить у пользователя число и проверить, входит ли оно в диапазон от 50 до 100 включительно.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите число:");
        if (int.TryParse(Console.ReadLine(), out int number))
        {
            Console.WriteLine(number >= 50 && number <= 100 ? "Число входит в диапазон." : "Число не входит в диапазон.");
        }
        else
        {
            Console.WriteLine("Введено некорректное значение.");
        }
    }
}
```

---

### Задача 4: Проверка символа на цифру

Программа должна запросить у пользователя символ и определить, является ли он цифрой.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите символ:");
        char symbol = Console.ReadKey().KeyChar;
        Console.WriteLine();

        if (char.IsDigit(symbol))
        {
            Console.WriteLine("Символ является цифрой.");
        }
        else
        {
            Console.WriteLine("Символ не является цифрой.");
        }
    }
}
```

---

### Задача 5: Сравнение двух чисел

Программа должна запросить у пользователя два числа и сообщить, какое из них больше, или что они равны.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите первое число:");
        if (double.TryParse(Console.ReadLine(), out double a))
        {
            Console.WriteLine("Введите второе число:");
            if (double.TryParse(Console.ReadLine(), out double b))
            {
                if (a > b) Console.WriteLine("Первое число больше второго.");
                else if (a < b) Console.WriteLine("Второе число больше первого.");
                else Console.WriteLine("Оба числа равны.");
            }
            else
            {
                Console.WriteLine("Второе число введено некорректно.");
            }
        }
        else
        {
            Console.WriteLine("Первое число введено некорректно.");
        }
    }
}
```


