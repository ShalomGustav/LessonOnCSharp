
# Домашнее задание по теме: Использование var, преобразование типов и частые ошибки в C#

## Задачи

### Задача 1: Конвертация типов
Напишите программу, которая:
- Запрашивает у пользователя два числа (целое и вещественное).
- Преобразует целое число в тип `double` и вещественное число в тип `int`.
- Выводит результат конвертации на экран.

**Решение**:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите целое число:");
        int integerNumber = int.Parse(Console.ReadLine());

        Console.WriteLine("Введите вещественное число:");
        double doubleNumber = double.Parse(Console.ReadLine());

        double convertedInteger = integerNumber;
        int convertedDouble = (int)doubleNumber;

        Console.WriteLine("Целое число в типе double: " + convertedInteger);
        Console.WriteLine("Вещественное число в типе int: " + convertedDouble);
    }
}
```

### Задача 2: Использование ключевого слова `var`
Создайте программу, которая:
- Использует `var` для объявления нескольких переменных с разными значениями (целое число, текст, число с плавающей точкой).
- Выводит тип каждой переменной на экран с помощью `GetType()`, чтобы показать, как компилятор автоматически определяет тип.

**Решение**:
```csharp
using System;

class Program
{
    static void Main()
    {
        var number = 42;
        var text = "Привет";
        var floatingNumber = 3.14;

        Console.WriteLine("Тип number: " + number.GetType());
        Console.WriteLine("Тип text: " + text.GetType());
        Console.WriteLine("Тип floatingNumber: " + floatingNumber.GetType());
    }
}
```

### Задача 3: Исправление типов (практика)
Дана программа с ошибками типов. Исправьте её, указав корректные типы данных.

Программа:

```csharp
public static void Main()
{
    var price = "100";
    var discount = 10.5;
    var quantity = "5";
    
    double total = (double)price * quantity - discount; // Ошибка
    Console.WriteLine("Итоговая цена: " + total);
}
```

**Решение**:
```csharp
using System;

class Program
{
    static void Main()
    {
        double price = 100.0;
        double discount = 10.5;
        int quantity = 5;

        double total = price * quantity - discount;
        Console.WriteLine("Итоговая цена: " + total);
    }
}
```

### Задача 4: Вычисление суммы округленных значений
Программа должна запросить у пользователя два вещественных числа, округлить их до целого и вывести сумму этих округленных значений.

**Решение**:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите первое вещественное число:");
        double num1 = double.Parse(Console.ReadLine());

        Console.WriteLine("Введите второе вещественное число:");
        double num2 = double.Parse(Console.ReadLine());

        int roundedSum = (int)Math.Round(num1) + (int)Math.Round(num2);
        Console.WriteLine("Сумма округленных значений: " + roundedSum);
    }
}
```

### Задача 5: Калькулятор с типами данных
Напишите программу-калькулятор, которая:
- Запрашивает у пользователя два числа (целое и вещественное).
- Выполняет над ними арифметические операции (сложение, вычитание, умножение, деление).
- Конвертирует результат каждой операции в `double` и выводит его на экран.

**Решение**:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите целое число:");
        int intNumber = int.Parse(Console.ReadLine());

        Console.WriteLine("Введите вещественное число:");
        double doubleNumber = double.Parse(Console.ReadLine());

        double sum = intNumber + doubleNumber;
        double difference = intNumber - doubleNumber;
        double product = intNumber * doubleNumber;
        double quotient = intNumber / doubleNumber;

        Console.WriteLine("Сумма: " + sum);
        Console.WriteLine("Разность: " + difference);
        Console.WriteLine("Произведение: " + product);
        Console.WriteLine("Частное: " + quotient);
    }
}
```

## Заключение
Эти задачи помогут вам лучше понять, как работать с различными типами данных и преобразованиями в C#. Выполните их самостоятельно, чтобы укрепить знания, полученные на уроке.

