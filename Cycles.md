#Циклы в Java

##while
Когда нужно повторить какое-то действие несколько раз, или повторять действие пока не произойдет какое-то событие - вам поможет цикл.

Первый вариант циклы которые выполняют действия пока выполняется действие - циклы while:
```Java
int a = 5;
while(a < 10)//Цикл быудет выполняться пока условие в скобках выполняется.
{
  a++;
}

while(a < 5)//Этот цикл не будет выполняться
{
  //какие-то действия
}

while(true)//Цикл будет бесконечно выполняться выводя числа по порядку.
{
  a++;
  System.out.println(a);
}
```
Это был while с предпроверкой условия. Есть другой вариант: while условие в котором проверяется после каждого шага цикла:
```Java
int a = 0;
do {
  System.out.println(a);
  a--;
} while (a >= -5);
//такой цикл выполнится 6 раз, написав значения от 0 до -6;
```

##for
Другим видом цикла является цикл повторяющий какое-то действие n раз.
Он состоит из трех частей:
```Java
for (инициализация; условие; итерация) {
  //тело цикла, т. е. действия повторяемые циклично
}
```
Блок инициализация выполняется единожды в начале цикла, блок условие проверяется перед каждой итерацией и блок итерация выполняется в конце каждой итерации.
Как это используется: простейший пример
```Java
//Сделать что-то 10 раз
for(int i=0; i<10;i++)
{
  //Какие-то действия
}
```
Пройтись по всем элементам массива:
```Java
//Цикл присвоит каждому элементу его индекс
int[] array = new int[10];
for(int i=0;i<array.length;i++)
{
  array[i] = i;
}
```
Блоки можно по разному менять
```Java
int[] array = new int[20];
int i = (int)Math.random()*20; //случайное целое число из промежутка [0;20)

for(;i<array.length-2;i+=2)
{
  array[i]*=i;
}

//цикл начнется со случайного индекса, будет идти по каждому второму элементу до предпредпоследнего элемента,
//умножая их на их индекс


for(;;)
{
}
//А этот цикл будет выполняться вечно так же как и while(true)
```

Еще один пример:
Представленная программа вычислит сумму элемнтов фрагмента последовательности 2, 5, 8,…,95,98.
```Java
int sum = 0; // Сюда будем накапливать результат
for (int j = 2; j <= 100; j=j+2) {
  sum = sum + j;
}
System.out.println(sum);
```
##break
Что если нужно прервать выполнение цикла по какой-то причине? Для этого нужен оператор break;
```Java
while(true)
{
  //какие-то действия
  if(shouldBreak()) //shouldBreak говорит, когда нужно выходить из цикла
    break;
}
```
Break выходит из цикла моментально, не заканчивая даже текущий шаг.

циклы можно маркировать, чтобы можно было выходить из внешнего цикла находясь во внутреннем. Пример:
```Java
outerloop:
for (int i=0; i < 5; i++) {
  for (int j=0; j < 5; j++) {
    if (i * j > 6) {
      System.out.println("Breaking");
      break outerloop;
    }
    System.out.println(i + " " + j);
  }
}
System.out.println("Done");
```
Этот пример выведет:
```
0 0
0 1
0 2
0 3
0 4
1 0
1 1
1 2
1 3
1 4
2 0
2 1
2 2
2 3
Breaking
Done
```
##continue
Оператор continue прерывает выполнение текущего шага и сразу переходит к выполнению следующего
```Java
//Вывести числа от 0 до 9, кроме тех, которые кратны трём
for(int i=0;i<10;i++)
{
  if(i%3==0)
    continue;
  System.out.println(i);
}
```