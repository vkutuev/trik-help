# Объект «script»

Представляет методы управления выполнением скрипта и доступ к функциям операционной системы.

| Метод                                       | Описание                                                                                                |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [quit](object-script.md#quit)               | Устанавливает флаг окончания работы для событийно-ориентированной программы.                            |
| [random](object-script.md#random)           | Возвращает случайное число из заданного диапазона.                                                      |
| [readAll](object-script.md#readall)         | Считывает всё содержимое указанного файла в массив строк.                                               |
| [removeFile](object-script.md#removefile)   | Удаляет указанный файл.                                                                                 |
| [run](object-script.md#run)                 | Устанавливает флаг событийно-ориентированной программы.                                                 |
| [system](object-script.md#system)           | Выполняет переданную в качестве параметра команду консоли операционной системы.                         |
| [time](object-script.md#time)               | Возвращает временной штамп — количество миллисекунд, прошедших с начала 1 января 1970 года по Гринвичу. |
| [timer](object-script.md#timer)             | Создаёт и возвращает таймер.                                                                            |
| [wait](object-script.md#wait)               | Приостанавливает выполнение скрипта на переданное количество миллисекунд.                               |
| [writeToFile](object-script.md#writetofile) | Записывает строку в файл.                                                                               |

## quit

Устанавливает флаг окончания работы для событийно-ориентированной программы. Как только будет завершён текущий обработчик события, исполнение скрипта закончится.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
script.quit()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
script.quit();	
```
{% endtab %}
{% endtabs %}

## random

Возвращает случайное число из заданного диапазона.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
script.random(min, max)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
script.random(min, max);
```
{% endtab %}
{% endtabs %}

В качестве параметров необходимо указать границы диапазона.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
a = script.random(0, 10) # случайное число от 0 до 10
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var a = script.random(0, 10); // случайное число от 0 до 10
```
{% endtab %}
{% endtabs %}

## readAll

Считывает всё содержимое указанного файла в массив строк.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
script.readAll("fileName")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
script.readAll("fileName");
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать название файла с расширением.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
lines = script.readAll("input.txt") # считывает текстовый файл input.txt
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var lines = script.readAll("input.txt"); // считывает текстовый файл input.txt
```
{% endtab %}
{% endtabs %}

## removeFile

Удаляет указанный файл.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
script.removeFile("fileName")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
script.removeFile("fileName");
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать название файла с расширением.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
script.removeFile("file.txt"); # удалить файл file.txt
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
script.removeFile("file.txt"); // удалить файл file.txt
```
{% endtab %}
{% endtabs %}

## run

Устанавливает флаг событийно-ориентированной программы. По окончанию работы скрипт не выгружается из памяти, а продолжает ждать наступления событий до тех пор, пока какой-либо из обработчиков не вызовет метод «[quit](object-script.md#quit)».

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
script.run()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
script.run();
```
{% endtab %}
{% endtabs %}

## system

Выполняет переданную команду.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
ript.system()
```
{% endtab %}

{% tab title="JavaScript" %}
```
script.system();
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать команду консоли операционной системы.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
script.system("reboot")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
script.system("reboot");
```
{% endtab %}
{% endtabs %}

## time

Возвращает временной штамп — количество миллисекунд, прошедших с начала 1 января 1970 года по Гринвичу.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
script.time()
```
{% endtab %}

{% tab title="JavaScript" %}
```
script.time();
```
{% endtab %}
{% endtabs %}

## timer

Создаёт и возвращает таймер (класс `«QTimer»`), посылающий сигнал `timeout` каждые n миллисекунд.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
script.timer(n)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
script.timer(n);
```
{% endtab %}
{% endtabs %}

В качестве параметра передаётся n .

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
def foo():
  print("It's Alive!!!")
tim = script.timer(500) # таймер на 500 мс
tim.timeout.connect(foo) # подписываем функцию foo на срабатывание по таймеру tim
script.wait(5000)
tim.stop()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
function foo(){
  print("It's Alive!!!")
}
tim = script.timer(500) // таймер на 500 мс
tim.timeout.connect(foo) // подписываем функцию foo на срабатывание по таймеру tim
script.wait(5000)
tim.stop()
```
{% endtab %}
{% endtabs %}

## wait

Приостанавливает выполнение скрипта на переданное количество миллисекунд.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
script.wait(msCount)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
script.wait(msCount);
```
{% endtab %}
{% endtabs %}

В качестве параметра передаётся количество миллисекунд.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
script.wait(1000) # остановить выполнение скрипта на одну секунду
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
script.wait(1000); // остановить выполнение скрипта на одну секунду
```
{% endtab %}
{% endtabs %}

## writeToFile

Записывает сроку в файл.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
script.writeToFile("fileName", "text")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
script.writeToFile("fileName", "text");
```
{% endtab %}
{% endtabs %}

В качестве параметров необходимо указать название файла и записываемую строку.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
script.writeToFile("output.txt", "Hello, world") # записать «Hello, world» в файл output.t
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
script.writeToFile("output.txt", "Hello, world"); // записать «Hello, world» в файл output.t
```
{% endtab %}
{% endtabs %}
