#Как можно работать с числовыми значениями.

```Java
//Целые числа:
int a = 20;
int b = 15;
int summ = a + b; //сложение, результат - 35;
int subtraction = a - b; //вычитание, результат - 5;
int multiplication = a * b; //умножение, результат - 300;
int division = a / b; //деление для целых чисел возвращает целую часть от деления: результат - 1;
int mod = a % b; //остаток от деления, результат - 5;

//Дробные числа:
double a = 20.5;
double b = 15.5;
double summ = a + b; //сложение, результат - 36.0;
double subtraction = a - b; //вычитание, результат - 5.0;
double multiplication = a * b; //умножение, резульат - 317.75;
double division = a / b; //деление, результат - 1.3225806451612903;
double mod = a % b; //остаток от деления, результат - 5.0;

//Cтроку в которой операция производится с предыдущим значением переменной можно записать сокращенно:
int a = 0;
int a = a + 5;
int a += 5; //сокращенная запись предыдущей строки
int a = a * 5;
int a *=5;//сокращенная запись предыдущей строки

//если необходимо увеличить/уменьшить переменную на один есть оператор ++/--:

int a = 0;
a++;// a == 1
a--;// a == 0
int b = a++;//если оператор ++ стоит после переменной,
//то операция вернет оригинальное значение переменной, т. е. b == 0, a == 1
int c = ++a;//иначе операция вернет новое значение переменной, c == 2 и a == 2
```