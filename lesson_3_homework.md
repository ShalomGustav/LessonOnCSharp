
# Домашнее задание по теме: использование TryParse, Char и преобразований данных

## Задачи

## Задача 1: Преобразование строки в целое число

Программа должна преобразовать строку `"25"` в число и вывести результат.

```csharp
string text = "25";
int.TryParse(text, out int number);
Console.WriteLine(number); // Результат: 25
```

## Задача 2: Преобразование символа в число

Программа должна преобразовать символ `'7'` в число.

```csharp
char digit = '7';
int number = int.Parse(digit.ToString());
Console.WriteLine(number); // Результат: 7
```

## Задача 3: Попытка преобразования некорректной строки

Программа должна попробовать преобразовать строку `"world"` в число. Если преобразование невозможно, результатом будет значение по умолчанию.

```csharp
string text = "world";
int.TryParse(text, out int number);
Console.WriteLine(number); // Результат: 0
```

## Задача 4: Преобразование строки с вещественным числом

Программа преобразует строку `"2.718"` в число типа `double`.

```csharp
string text = "2.718";
double.TryParse(text, out double number);
Console.WriteLine(number); // Результат: 2.718
```


## Задача 5: Определение кода символа и его арифметическое использование

Программа определяет числовой код символа `'A'` и добавляет к нему число `5`.

```csharp
char letter = 'A';
int code = (int)letter;
int result = code + 5;
Console.WriteLine(result); // Результат: 70
```

