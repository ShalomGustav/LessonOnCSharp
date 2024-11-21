
# Урок 2: Использование var, преобразование типов и частые ошибки

## Как создать проект в Visual Studio

Перед началом работы создадим новый проект в Visual Studio. Следуйте инструкциям из первого урока для создания консольного приложения.

## Теория

В этом уроке мы разберем ключевые концепции, связанные с типами данных в C#, такие как использование ключевого слова `var`, преобразование типов и распространенные ошибки, которые встречаются у начинающих программистов.

## 1. Ключевое слово `var`

В C# ключевое слово `var` позволяет компилятору автоматически определять тип переменной на основе значения, присваиваемого этой переменной. Например:
```csharp
var number = 10; // Тип будет определен как int
var text = "Hello"; // Тип будет определен как string
```

Важно помнить, что использование `var` оправдано только в случаях, когда тип очевиден из контекста, или для удобства в более сложных ситуациях. В остальных случаях рекомендуется явно указывать тип для повышения читаемости кода.

## 2. Преобразование типов

Иногда бывает необходимо преобразовать значение из одного типа в другой. В C# существуют:
- **Неявное преобразование** — автоматическое преобразование компилятором, если нет риска потери данных (например, int -> long).
- **Явное преобразование** — используется при возможности потери данных. Для этого применяются операторы приведения (например, `(int)` или методы, такие как `Convert.ToInt32`).

Примеры:
```csharp
// Неявное преобразование
int smallNumber = 42;
double largeNumber = smallNumber; // int -> double

// Явное преобразование
double someValue = 9.7;
int roundedValue = (int)someValue; // double -> int (теряется дробная часть)
```
## Пояснение по типам данных в C#

1. **double**  
   Используется для хранения вещественных чисел (чисел с дробной частью), занимает 8 байт памяти. Подходит для точных вычислений.  
   Пример: double num1 = +5.5e-2;. Сохраняет значение 0.055 в научной нотации.

2. **float**  
   Также используется для хранения вещественных чисел, но занимает 4 байта памяти и имеет меньшую точность, чем double. Подходит, когда точность не критична.  
   Пример: float num2 = 7.8f;. Сохраняет значение 7.8. Суффикс f указывает, что это float.

3. **int**  
   Хранит целые числа в диапазоне от -2,147,483,648 до 2,147,483,647 и занимает 4 байта. Широко используется для работы с целыми числами.  
   Пример: int num3 = 0;.  Инициализируется нулем.

4. **long**  
   Тип данных для больших целых чисел, занимает 8 байт и поддерживает значительно больший диапазон значений, чем int. Используется для хранения очень больших целых чисел.  
   Пример: long num4 = 2000000000000L;. Суффикс L указывает, что это long.
   
## 3. Частые ошибки с типами данных

Ошибка при указании типа данных — одна из самых частых у начинающих программистов. Неправильный выбор типа может вызвать ошибки компиляции или неожиданные результаты.

## Практическая работа

### Задача 1: Исправление типов данных

**Программа**:

```csharp
public static void Main()
{
    double pi = Math.PI;
    int tenThousand = 10000L; // Исправьте тип
    float tenThousandPi = pi * tenThousand; // Исправьте тип
    int roundedTenThousandPi = tenThousandPi; // Исправьте тип
    int integerPartOfTenThousandPi = tenThousandPi; // Исправьте тип
    Console.WriteLine(integerPartOfTenThousandPi);
    Console.WriteLine(roundedTenThousandPi);
}
```

**Решение**:

```csharp
using System;

class Program
{
    static void Main()
    {
        double pi = Math.PI;
        int tenThousand = 10000; // Убрано "L" для int
        double tenThousandPi = pi * tenThousand; // Изменено на double для точности
        int roundedTenThousandPi = (int)Math.Round(tenThousandPi); // Приведение с округлением
        int integerPartOfTenThousandPi = (int)tenThousandPi; // Приведение к int для целой части
        Console.WriteLine(integerPartOfTenThousandPi);
        Console.WriteLine(roundedTenThousandPi);
    }
}
```

## Задача 2: Округление до целого

**Программа**:

```csharp
public static void Main()
{
    double amount = 1.11; // количество биткоинов от одного человека
    int peopleCount = 60; // количество человек
    int totalMoney = (int) amount * peopleCount; // Исправьте строку
    Console.WriteLine(totalMoney);
}
```

**Решение**:

```csharp
using System;

class Program
{
    static void Main()
    {
        double amount = 1.11; // Количество биткоинов от одного человека
        int peopleCount = 60; // Количество человек
        int totalMoney = (int)(amount * peopleCount); // Округление суммы
        Console.WriteLine(totalMoney);
    }
}
```

## Задача 3: Преобразование строки в число

**Программа**:

```csharp
public static void Main()
{
    string doubleNumber = "894376.243643";
    int number = doubleNumber; // Исправьте строку
    Console.WriteLine(number + 1);
}
```

**Решение**:

```csharp
using System;

class Program
{
    static void Main()
    {
        string doubleNumber = "894376,243643";
        int number = (int)double.Parse(doubleNumber); // Преобразование строки в double и приведение к int
        //int number = Convert.ToInt32(doubleNumber);
        Console.WriteLine(number + 1);
    }
}
```
```csharp
#Инвариант культуры если передается точка в качестве разделителя:
string doubleNumber = "894376.243643";
int number = (int)double.Parse(doubleNumber,CultureInfo.InvariantCulture);
```
## Задача 4: Половинка числа

**Программа**:

```csharp
static public void Main()
{
    var a = 5; // Исправьте эту строку
    a += 0.5;
    Console.WriteLine(a);
}
```

**Решение**:

```csharp
using System;

class Program
{
    static public void Main()
    {
        double a = 5; // Приведение к типу double для точности
        a += 0.5;
        Console.WriteLine(a);
    }
}
```

## Задача 5: Калькулятор с преобразованием типов

Создайте программу-калькулятор, которая:
- Запрашивает у пользователя два числа: одно целое и одно вещественное.
- Выполняет над ними четыре арифметические операции (сложение, вычитание, умножение, деление).
- Выводит результат каждой операции, используя преобразование типов, где это необходимо.

**Подсказка**: Обратите внимание на то, что результат операций может требовать преобразования типов для точного отображения. Программа должна позволять складывать `int` и `double`, выводя результат как `double`. Аналогично, используйте преобразование для других операций, чтобы избежать потери данных.


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



### Задача 5: Калькулятор с преобразованием типов

Создайте программу-калькулятор, которая:
- Запрашивает у пользователя два числа: одно целое и одно вещественное.
- Выполняет над ними четыре арифметические операции (сложение, вычитание, умножение, деление).
- Выводит результат каждой операции, используя преобразование типов, где это необходимо.

**Подсказка**: Обратите внимание на то, что результат операций может требовать преобразования типов для точного отображения. Программа должна позволять складывать `int` и `double`, выводя результат как `double`. Аналогично, используйте преобразование для других операций, чтобы избежать потери данных.

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

        // Сложение
        double sum = intNumber + doubleNumber;
        Console.WriteLine("Сумма: " + sum);

        // Вычитание
        double difference = intNumber - doubleNumber;
        Console.WriteLine("Разность: " + difference);

        // Умножение
        double product = intNumber * doubleNumber;
        Console.WriteLine("Произведение: " + product);

        // Деление
        double quotient = intNumber / doubleNumber;
        Console.WriteLine("Частное: " + quotient);
    }
}
```
