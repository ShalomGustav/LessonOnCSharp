### Урок 7: Методы в C#

---

## Теория

Методы в C# позволяют организовать код в блоки, которые можно многократно использовать. Они помогают сделать код более структурированным, читаемым и удобным для сопровождения.

---

### Основные элементы методов

1. **Сигнатура метода**  
   Сигнатура включает:
   - Имя метода.
   - Последовательность типов аргументов.  
   Пример:  
   ```csharp
   static int Multiply(int a, int b)
   {
       return a * b;
   }
   ```

2. **Возвращаемый тип**  
   Указывается перед именем метода и определяет тип значения, которое метод возвращает. Если метод ничего не возвращает, используется `void`.  
   Пример:  
   ```csharp
   static void PrintMessage(string message)
   {
       Console.WriteLine(message);
   }
   ```

3. **Как правильно подписывать методы**  
   - Используйте глаголы в названии метода, чтобы показать, что он делает. Например, `CalculateSum`, `PrintMessage`.
   - Если метод возвращает значение, название должно отражать, что именно возвращается. Например, `GetMaximum` для возврата максимального значения.
   - Название метода должно быть в PascalCase.

4. **Модификатор `static`**  
   Модификатор `static` означает, что метод принадлежит классу, а не его экземпляру. На текущем этапе будем использовать `static` для всех методов, чтобы упростить работу.

5. **Аргументы метода**  
   Метод может принимать входные данные через аргументы. Они указываются в круглых скобках после имени метода.  
   Пример:
   ```csharp
   static int Add(int x, int y)
   {
       return x + y;
   }
   ```
   - Каждый аргумент должен иметь понятное имя, отражающее его назначение.

6. **`return`**  
   Если метод возвращает значение, используется оператор `return`. Оператор завершает выполнение метода и возвращает указанное значение. Если возвращаемый тип `void`, `return` можно опустить.  
   Пример:
   ```csharp
   static double Divide(double a, double b)
   {
       return a / b;
   }
   ```

7. **Перегрузка методов**  
   В C# можно создавать методы с одинаковым именем, но разными аргументами. Это называется перегрузкой методов.  
   Пример:
   ```csharp
   static void Print(int number)
   {
       Console.WriteLine(number);
   }

   static void Print(int number, int anotherNumber)
   {
       Console.WriteLine(number);
       Console.WriteLine(anotherNumber);
   }
   ```

8. **Сокращённая запись методов**
   Если метод выполняет одно простое действие, его можно записать в сокращённой форме с использованием символа `=>` (так называемое "выражение тела метода").

   **Описание `=>`:**
   - `=>` заменяет фигурные скобки `{}` и ключевое слово `return` для методов, выполняющих одно действие.
   - Упрощённая запись делает код более компактным и удобным для чтения.

   **Примеры использования `=>`:**
   ```csharp
   static int Multiply(int a, int b) => a * b;
   ```
   Эквивалент в стандартной записи:
   ```csharp
   static int Multiply(int a, int b)
   {
       return a * b;
   }
   ```

   Для методов без возвращаемого значения (`void`):
   ```csharp
   static void PrintMessage(string message) => Console.WriteLine(message);
   ```
   Эквивалент в стандартной записи:
   ```csharp
   static void PrintMessage(string message)
   {
       Console.WriteLine(message);
   }
   ```  
   Если метод выполняет одно простое действие, его можно записать в сокращённой форме с использованием символа `=>` (так называемое "выражение тела метода").  
   Пример:
   ```csharp
   static int Multiply(int a, int b) => a * b;
   ```

9. **Как правильно вызывать методы и где их вызывать**  
   - Методы вызываются по их имени. Если метод принимает параметры, их необходимо передать в круглых скобках.
   - Методы вызываются в теле других методов, например, в методе `Main()`, который является точкой входа программы.
   Пример:
   ```csharp
   static int Add(int a, int b)
   {
       return a + b;
   }

   static void Main()
   {
       int sum = Add(5, 10); // Вызов метода Add
       Console.WriteLine($"Сумма: {sum}");
   }
   ```
   - Если метод возвращает значение, результат вызова можно сохранить в переменной или использовать в выражении.
   - Если метод не возвращает значения (`void`), его вызов используется как самостоятельная инструкция.

---

## Практические задания

### Задача 1: Сумма двух чисел
Создайте метод, который принимает два числа и возвращает их сумму. Вызовите этот метод из `Main()` и выведите результат.

**Пример кода**:
```csharp
using System;

class Program
{
    static int Add(int a, int b)
    {
        return a + b;
    }

    static void Main()
    {
        int result = Add(5, 7);
        Console.WriteLine($"Сумма: {result}");
    }
}
```

---

### Задача 2: Перегрузка метода для вывода сообщений
Создайте два метода `PrintMessage`: один принимает строку, а второй — строку и число. Вызовите оба метода из `Main()`.

**Пример кода**:
```csharp
using System;

class Program
{
    static void PrintMessage(string message)
    {
        Console.WriteLine(message);
    }

    static void PrintMessage(string message, int number)
    {
        Console.WriteLine($"{message} {number}");
    }

    static void Main()
    {
        PrintMessage("Привет!");
        PrintMessage("Ваш результат:", 42);
    }
}
```

---

### Задача 3: Определение минимального числа
Создайте метод, который принимает два числа и возвращает меньшее из них. Вызовите метод из `Main()`.

**Пример кода**:
```csharp
using System;

class Program
{
    static int Min(int a, int b)
    {
        return a < b ? a : b;
    }

    static void Main()
    {
        Console.WriteLine("Введите первое число:");
        int x = int.Parse(Console.ReadLine());

        Console.WriteLine("Введите второе число:");
        int y = int.Parse(Console.ReadLine());

        Console.WriteLine($"Минимальное число: {Min(x, y)}");
    }
}
```

---

### Задача 4: Определение чётности числа
Создайте метод, который принимает одно число и возвращает строку "Чётное" или "Нечётное". Вызовите метод из `Main()` и выведите результат.

**Пример кода**:
```csharp
using System;

class Program
{
    static string CheckEvenOdd(int number)
    {
        return number % 2 == 0 ? "Чётное" : "Нечётное";
    }

    static void Main()
    {
        Console.WriteLine("Введите число:");
        int num = int.Parse(Console.ReadLine());
        Console.WriteLine($"Число {num} является {CheckEvenOdd(num)}.");
    }
}
```

---

### Задача 5: Умножение с выводом результата
Создайте метод, который принимает два числа, умножает их и выводит результат. Метод не возвращает значение (используйте `void`). Вызовите метод из `Main()`.

**Пример кода**:
```csharp
using System;

class Program
{
    static void MultiplyAndPrint(int a, int b)
    {
        Console.WriteLine($"Результат умножения: {a * b}");
    }

    static void Main()
    {
        Console.WriteLine("Введите первое число:");
        int x = int.Parse(Console.ReadLine());

        Console.WriteLine("Введите второе число:");
        int y = int.Parse(Console.ReadLine());

        MultiplyAndPrint(x, y);
    }
}
```

