# Урок: Конструкция `switch-case` в C#

## Теория

В этом уроке мы разберём:
- Как работает оператор `switch`.
- Сравнение `switch` с `if-else`.
- Правильное использование `switch-case` в C#.
- Типичные ошибки и их решение.

---

### 1. Оператор `switch`

Оператор `switch` используется для выбора одной из нескольких возможных ветвей выполнения кода на основе значения выражения.

#### Синтаксис:
```csharp
switch (выражение)
{
    case значение1:
        // Код для значения1
        break;
    case значение2:
        // Код для значения2
        break;
    // Другие case
    default:
        // Код, если ни одно из значений не подошло
        break;
}
```

#### Пример:
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
                case 12:
                case 1:
                case 2:
                    Console.WriteLine("Зима");
                    break;
                case 3:
                case 4:
                case 5:
                    Console.WriteLine("Весна");
                    break;
                case 6:
                case 7:
                case 8:
                    Console.WriteLine("Лето");
                    break;
                case 9:
                case 10:
                case 11:
                    Console.WriteLine("Осень");
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

### 2. Когда использовать `switch`

Используйте `switch`, когда:
- Условий больше двух.
- Проверяется одно выражение на несколько значений.
- Все ветви взаимно исключают друг друга.

---

### 3. Преимущества и недостатки

#### Преимущества:
- Повышает читаемость кода.
- Может быть производительнее, чем серия `if-else`.

#### Недостатки:
- Работает только с конкретными значениями (не интервалами).
- Может стать громоздким при добавлении большого количества `case`.

---

## Практические задания

### Задача 1: Название дня недели
Напишите программу, которая по номеру дня недели выводит его название.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите номер дня недели (1–7):");
        if (int.TryParse(Console.ReadLine(), out int day))
        {
            switch (day)
            {
                case 1:
                    Console.WriteLine("Понедельник");
                    break;
                case 2:
                    Console.WriteLine("Вторник");
                    break;
                case 3:
                    Console.WriteLine("Среда");
                    break;
                case 4:
                    Console.WriteLine("Четверг");
                    break;
                case 5:
                    Console.WriteLine("Пятница");
                    break;
                case 6:
                    Console.WriteLine("Суббота");
                    break;
                case 7:
                    Console.WriteLine("Воскресенье");
                    break;
                default:
                    Console.WriteLine("Неверный номер дня.");
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

### Задача 2: Простейший калькулятор
Напишите программу, которая принимает два числа и оператор (`+`, `-`, `*`, `/`), а затем выполняет соответствующую операцию.

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
                Console.WriteLine("Введите оператор (+, -, *, /):");
                char operation = Console.ReadLine()[0];

                switch (operation)
                {
                    case '+':
                        Console.WriteLine($"Результат: {a + b}");
                        break;
                    case '-':
                        Console.WriteLine($"Результат: {a - b}");
                        break;
                    case '*':
                        Console.WriteLine($"Результат: {a * b}");
                        break;
                    case '/':
                        if (b != 0)
                            Console.WriteLine($"Результат: {a / b}");
                        else
                            Console.WriteLine("Ошибка: деление на ноль.");
                        break;
                    default:
                        Console.WriteLine("Неверный оператор.");
                        break;
                }
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

---

### Задача 3: Определение времени года
Программа должна запросить у пользователя номер месяца и вывести соответствующее время года.

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
                case 12:
                case 1:
                case 2:
                    Console.WriteLine("Зима");
                    break;
                case 3:
                case 4:
                case 5:
                    Console.WriteLine("Весна");
                    break;
                case 6:
                case 7:
                case 8:
                    Console.WriteLine("Лето");
                    break;
                case 9:
                case 10:
                case 11:
                    Console.WriteLine("Осень");
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

### Задача 4: Проверка чётности числа
Напишите программу, которая запрашивает у пользователя число и проверяет, является ли оно чётным.

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
                case 1:
                case -1:
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

### Задача 5: Распознавание символа
Напишите программу, которая запрашивает у пользователя символ и определяет, является ли он буквой, цифрой или специальным символом.

`Решение основанное на методах`

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите символ:");
        char input = Console.ReadKey().KeyChar;
        Console.WriteLine();

        switch (input)
        {
            case char c when char.IsLetter(c):
                Console.WriteLine("Это буква.");
                break;
            case char c when char.IsDigit(c):
                Console.WriteLine("Это цифра.");
                break;
            default:
                Console.WriteLine("Это специальный символ.");
                break;
        }
    }
}
```

`Решение основанное на кодировке`

```csharp
using System;

public class Program
    {
        static void Main(string[] args)
        {
            char.TryParse(Console.ReadLine(), out var charSymbol);
            int numASCI = charSymbol;
            bool number = numASCI >= 48 && numASCI <= 57;
            switch (number)
            {
                case true:
                    Console.WriteLine("Numeric");
                    break;
                case false:
                    bool is_char = (numASCI >= 65 && numASCI <= 90) || (numASCI >= 97 && numASCI <= 122);
                    switch (is_char)
                    {
                        case true:
                            Console.WriteLine("Char");
                            break;
                        case false:
                            Console.WriteLine("Special symbol");
                            break;
                    }
                    break;
            }
            Console.ReadKey();
        }
    }
```
