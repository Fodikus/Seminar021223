# Seminar021223
Домашняя работа №6 к семинару "Знакомство с языками программирования"

# Задача 41: Пользователь вводит с клавиатуры M чисел. Посчитайте, сколько чисел больше 0 ввёл пользователь.
```
Console.Clear();
Console.Write("Введите количество чисел M, которое вы будете вводить: ");
int m = Convert.ToInt32(Console.ReadLine());

int[] array = new int[m];
int s = 0;
for (int i = 0; i < m; i++)
{
    Console.Write($"Введите число N{i + 1}: ");
    int n = Convert.ToInt32(Console.ReadLine());
    array[i] = n;
    if (n > 0)
        s++;
}

Console.WriteLine($"Количество чисел больше: [{string.Join(", ", array)}] -> {s} ");
```

# Задача 43: Напишите программу, которая найдёт точку пересечения двух прямых, заданных уравнениями y = k1 * x + b1, y = k2 * x + b2; значения b1, k1, b2 и k2 задаются пользователем.
```
Console.Clear();
Console.Write("Введите значение b1: ");
double b1 = Convert.ToDouble(Console.ReadLine());
Console.Write("Введите значение k1: ");
double k1 = Convert.ToDouble(Console.ReadLine());
Console.Write("Введите значение b2: ");
double b2 = Convert.ToDouble(Console.ReadLine());
Console.Write("Введите значение k2: ");
double k2 = Convert.ToDouble(Console.ReadLine());

double x = Math.Round(((b2 - b1) / (k1 - k2)), 2);
double y = Math.Round((k1 * x + b1), 2);

Console.WriteLine($"b1={b1}, k1={k1}, b2={b2}, k2={k2} -> ({x};{y}) ");
```

# Рекурсия(https://acmp.ru/asp/do/index.asp?main=task&id_course=1&id_section=9&id_topic=123&id_problem=765)
```
Console.Clear();
Console.Write("Введите строку состоящую из N символов: ");
string N = Console.ReadLine();
while ((N.Length < 2) || (N.Length > 8))
{
    Console.WriteLine($"Вы ошиблись! Максимальное кол-во символов не должно превышать 8 и не должно быть меньше 1! \nВведите строку состоящую из N символов: ");
    N = Console.ReadLine();
}

char[] ch = new char[N.Length]; 
for (int s = 0; s < N.Length; s++) 
{ 
    ch[s] = N[s]; 
} 

void Permutations(char[] str, int i, int n)
{
    if (str[i] == str[n - 1])
    {
        Console.WriteLine($"Результат: {string.Join("", str)};");
        return;
    }

    for (int j = i; j < n; j++)
    {
        (str[i], str[j]) = (str[j], str[i]);
        Permutations(str, i + 1, n);
        (str[i], str[j]) = (str[j], str[i]);       
    }
}

Permutations(ch, 0, N.Length);
```

# Площадь треугольника(https://acmp.ru/asp/do/index.asp?main=task&id_course=1&id_section=6&id_topic=116&id_problem=719)
```
Console.Clear();
string k = "";
Console.Write("Введите координата x1 вершины угла А: ");
int x1 = Convert.ToInt32(Console.ReadLine());
k = k + x1 + " ";
Console.Write("Введите координата y1 вершины угла А: ");
int y1 = Convert.ToInt32(Console.ReadLine());
k = k + y1 + " ";
Console.Write("Введите координата x2 вершины угла B: ");
int x2 = Convert.ToInt32(Console.ReadLine());
k = k + x2 + " ";
Console.Write("Введите координата y2 вершины угла B: ");
int y2 = Convert.ToInt32(Console.ReadLine());
k = k + y2 + " ";
Console.Write("Введите координата x3 вершины угла C: ");
int x3 = Convert.ToInt32(Console.ReadLine());
k = k + x3 + " ";
Console.Write("Введите координата y3 вершины угла C: ");
int y3 = Convert.ToInt32(Console.ReadLine());
k = k + y3;

double a = Math.Sqrt(Math.Pow((x2 - x1), 2) + Math.Pow((y2 - y1), 2));
double b = Math.Sqrt(Math.Pow((x3 - x2), 2) + Math.Pow((y3 - y2), 2));
double c = Math.Sqrt(Math.Pow((x1 - x3), 2) + Math.Pow((y1 - y3), 2));
double p = (a + b + c) / 2.0;
double s = Math.Sqrt(p * (p - a) * (p - b) * (p - c));

Console.WriteLine($"{k}: {Math.Round(s, 2)}");
```
