# Массив

Массив — один из [типов языка TRIK Studio](./), хранящий набор значений (элементов массива), идентифицируемых по индексу. Нумерация индексов в массиве начинается с 0.

Массивы можно создавать явно, используя следующие выражения (варианты записи равносильны):

```
a = {1; 2; 3; 4};
a = {1, 2, 3, 4};
```

Или с явным указанием индексов:

```
a = {[0] = 1, [10] = 2, [20] = 3};
```

Можно использовать массивы, не создавая их. Например, так:

```
a[1] = 1;
a[2] = 2;
```

При этом «пустые места» в массиве (индексы, которым не было явного присваивания) будут заполнены значениями по умолчанию:

* `0` — для **целых** и **вещественных**;
* `false` _**** —_ для **булевых**;
* _пустыми строками_ для **строковых** массивов.

Значения массива также могут использоваться без фигурных скобок, если используются в качестве возвращаемого значения. Например, данное выражение вернёт массив из чисел `1` и `2`:

```
a = 1;
b = 2;
a, b 
```

Сделано это для того, чтобы интерпретировать перечисления значений (например, порты моторов в блоке [«Моторы вперёд»](../../../../trik/programming-visual/blocks.md)) как массивы. Поэтому везде, где используется запись значений через запятую, можно использовать массив.