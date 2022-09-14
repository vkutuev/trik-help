# Добавление ограничений в 2D-модель

* [Структура описания ограничений](./#struktura-napisaniya-ogranichenii)
* [Условия](./#usloviya)
* [Атомарные условия](./#atomarnye-usloviya)
* [Типы переменных и арифметические операции](./#tipy-peremennykh-i-arifmeticheskie-operacii)
* [Триггеры](./#triggery)
* [Названия датчиков](./#nazvaniya-datchikov)
* [Дополнительные свойства робота](./#dopolnitelnye-svoistva-robota)
* [Работа с экраном контроллера](./#rabota-s-ekranom-kontrollera)
* [Пример добавления ограничений](./#primer-dobavleniya-ogranichenii)

Для подготовки [упражнений](../../exercises.md) для учеников существует возможность внесения ограничений с помощью [редактирования XML-файла](../settings.md).

Ограничения бывают трех видов:

1. **Временны́е.**\
   Например, лимит времени на исполнение задачи или конкретное действие в конкретный временной отрезок.\

2. **Пространственные.**\
   Например, добавление регионов («Старт», «Финиш») или запрет / принуждение робота, его датчика или какого-то подвижного предмета находиться в определенные промежутки времени в определенном месте.\

3. **Ограничения на устройства.**\
   Например, ограничение на набор датчиков или на поведение устройств.

## Структура написания ограничений

Для описания ограничений используется главный тег [`<constraints>…</constraints>`](./#less-than-constraints-greater-than-less-than-constraints-greater-than), в который вписываются все ограничения. Используется как контейнер. Ограничения описываются внутри тега, каждый дочерний тег должен быть одним из четырех:

| Тег                                                                                  | Описание                                                                                  |
| ------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| [timelimit](./#less-than-timelimit-greater-than)                                     | Временное ограничение.                                                                    |
| [constraint](./#less-than-constraint-greater-than-less-than-constraint-greater-than) | Ограничение с произвольным условием, при нарушении которого будет выдана заданная ошибка. |
| [event](./#event)                                                                    | Основной инструмент задания динамических ограничений. Используется как контейнер.         |
| [init](./#init)                                                                      | Безусловное событие, выполняющееся перед началом выполнения программы.                    |

## \<constraints>...\</constraints>

Основной тег, в который вписываются все ограничения. Используется как контейнер.

```markup
<constraints>
     <!-- Временное ограничение -->
     <timelimit value="30000"/>
     
     <!-- Ограничение с условием. При нарушении условия будет выдана ошибка -->
     <constraint checkOnce="true" failMessage="Робот должен находиться на старте перед запуском!">
          <inside objectId="robot1" regionId="start_zone"/>
     </constraint>
     
     <!-- Инициализация переменной x со значением 2 -->
     <init>
          <setter name="x">
               <int value="2"/>
          </setter>
      </init>

</constraints>
```

## \<timelimit/>

Временное ограничение. Является обязательным.

#### Атрибуты

| Атрибут              | Описание                                                                                                    |
| -------------------- | ----------------------------------------------------------------------------------------------------------- |
| **value="значение"** | Количество миллисекунд, через которое исполнение будет прекращено и выдана ошибка «Превышен лимит времени». |

#### Синтаксис

```markup
<timelimit value="35000"/>
```

## \<constraint>...\</constraint>

Ограничение с произвольным условием, при нарушении которого будет выдана заданная ошибка. Может использоваться как контейнер. Имеет один дочерний тег: `<conditions>...</conditions>`.

#### Атрибуты

| Атрибут                   | Описание                                                                                                                                                                                                                                                                               |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **checkOnce="true"**      | <p>Логический атрибут. Если в значении стоит true, то ограничение будет проверено 1 раз при старте программы и больше проверяться не будет.</p><p>Полезно, например, если нужно 1 раз проверить, что датчики расставлены верно, а дальше во время исполнения ничего не поменяется.</p> |
| **failMessage="Ошибка!"** | Сообщение об ошибке, которое будет показано при нарушении ограничения.                                                                                                                                                                                                                 |

#### Синтаксис

```markup
<constraint checkOnce="true" failMessage="Робот должен находиться на старте перед запуском!">
```

```markup
<!-- Проверяет при запуске, что на порту А1 установлен инфракрасный датчик расстояния -->
<constraint checkOnce="true" failMessage="У робота должен быть установлен инфракрасный датчик расстояния на порту А1">
    <equals>
        <typeOf objectId="robot1.A1"/>
        <string value="twoDModel::robotModel::parts::RangeSensor"/>
    </equals>
</constraint>
```

```markup
<!-- Проверяет, что робот находится в допустимом регионе на протяжении всего времени выполнения программы -->
<constraint failMessage="Робот покинул допустимую зону!">
    <inside objectId="robot1" regionId="warzone"/>
</constraint>
```

## \<event>...\</event> <a href="#event" id="event"></a>

Основной инструмент задания динамических ограничений. Используется как контейнер.

Событие - это просто пара ([условие](./#usloviya), [триггер](./#triggery)).

#### Атрибуты

| Атрибут                       | Описание                                                                                                                                                                                                                                                                                                |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **settedUpInitially="true"**  | Атрибут, позволяющий указать взведено ли событие при старте программы. Событие может быть взведено или спущено (setted up и dropped). Во взведенном состоянии событие выполняет свой триггер по выполнению своего условия, в спущенном оно просто игнорируется системой. Значение по умолчанию — false. |
| **id="finish checker"**       | Уникальный идентификатор события. По этому идентификатору можно обращаться к данному событию из других. Опциональный.                                                                                                                                                                                   |
| **dropsOnFire = "true"**      | Логический атрибут, который указывает, продолжать ли быть событию взведенным после его срабатывания или нет. Опциональный. Значение по умолчанию -- true.                                                                                                                                               |

#### Синтаксис

```markup
<event id="finish checker" settedUpInitially="false">
	<condition>
		<inside objectId="robot1" regionId="finish"/>
	</condition>
	<trigger>
		<success/>
	</trigger>
</event>
```

## \<init>...\</init> <a href="#init" id="init"></a>

Безусловное событие, выполняющееся перед началом выполнения программы.&#x20;

#### Пример

```markup
<!-- Перед началом выполнения программы заводим переменную "my_value" со значением два -->
<init>
    <setter name="my_value">
        <int value="2"/>
    </setter>
</init>
```

## Условия

Теперь обсудим, какими могут быть условия в элементах [\<constraint>](./#less-than-constraint-greater-than-less-than-constraint-greater-than) и [\<event>](./#event). Условия задаются с помощью тега [\<condition>](./#condition) в случае, если проверяется только одно из [атомарных условий](./#atomarnye-usloviya), или тега [\<conditions>](./#less-than-conditions-greater-than-less-than-conditions-greater-than), если проверяется составное условие.

## \<condition>...\</condition> <a href="#condition" id="condition"></a>

Внутри этого тега описывается проверяемое условие.

#### Пример

```markup
<condition>
    <!-- Внутри тега описано условие равенства двух значений -->
    <equals>
        <objectState object="robot1.display.smiles"/>
        <bool value="true"/>
    </equals>
</condition>
```

## \<conditions>...\</conditions>

Используется для создания составных условий. Обязательным атрибутом должна быть указана логическая связка. Связкой может быть `and` или `or`. Отрицание выражения задается тегом `<not>` без атрибутов. Среди подвыражений могут также встречаться другие элементы \<conditions>.

#### Атрибуты

| Атрибут        | Описание           |
| -------------- | ------------------ |
| **glue="and"** | Логическая связка. |

#### Синтаксис

```markup
<conditions glue="and">
   <!-- Условие1 -->
   <!-- Условие2 -->
   <!--    ...   -->
   <!-- УсловиеN -->
</conditions>

<conditions glue="and">
   <not>
      <!-- Условие1 -->
   </not>
</conditions>

<conditions glue="and">
   <timer timeout="1000" forceDropOnTimeout="true"/>
   <conditions glue="or">
      <greater>
         <objectState object="robot1.display.labels.size"/>
         <int value="20"/>
      </greater>
      <less>
         <objectState object="robot1.display.labels.size"/>
         <int value="19"/>
       </less>    
    </conditions>
</conditions>
```

## Атомарные условия

Атомарное условие представляет собой один из следующих элементов:

| Тег                                                                                  | Описание                                                                       |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| [equals](./#equals), [notEqual](./#notequal), [greater](./#greater), [less](./#less) | Операции сравнения значений.                                                   |
| ****[inside](./#inside)                                                              | Позволяет задавать пространственные ограничения.                               |
| [settedUp и dropped](./#settedup)                                                    | Позволяет проверить, взведено событие или нет.                                 |
| [timer](./#timer)                                                                    | Позволяет задать время в мс, после которого данное условие считается истинным. |

## \<equals>...\</equals> <a href="#equals" id="equals"></a>

Равно. Операция сравнения значений функциональных символов. Может использоваться как контейнер.

#### Синтаксис

```markup
<equals>
	<objectState object="robot1.display.labels.first.text"/>
	<string value="finish"/>
</equals>
```

## \<notEqual>...\</notEqual> <a href="#notequal" id="notequal"></a>

Не равно. Операция сравнения значений функциональных символов. Может использоваться как контейнер.

#### Синтаксис

```markup
<notEqual>
	<objectState object="robot1.display.labels.first.text"/>
	<string value="finish"/>
</notEqual>
```

## \<greater>...\</greater> <a href="#greater" id="greater"></a>

Больше. Операция сравнения значений функциональных символов. Может использоваться как контейнер.

#### Синтаксис

```markup
<greater>
	<objectState object="robot1.display.labels.size"/>
	<int value="0"/>
</greater>
```

## \<less>...\</less> <a href="#less" id="less"></a>

Меньше. Операция сравнения значений функциональных символов. Может использоваться как контейнер.

#### Синтаксис

```markup
<less>
    <objectState object="robot1.display.labels.size"/>
    <int value="10"/>
</less>
```

## \<inside/> <a href="#inside" id="inside"></a>

Позволяет задавать пространственные ограничения.

#### Атрибуты

| Атрибут                            | Описание                                                                                                                                                                                  |
| ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **objectId="id"**                  | id взятого объекта.                                                                                                                                                                       |
| **regionId="id"**                  | id взятого региона.                                                                                                                                                                       |
| **objectPoint="center\|all\|any"** | <p>Осуществляет проверку того, что:</p><p>center — центр объекта находится в зоне,<br>all — все точки объекта находятся в зоне,<br>any — хоть какая-то точка объекта находится в зоне</p> |

#### Синтаксис

```markup
<!-- Задаем ограничение на то, что объект робот находится в регионе с id=”start” -->
<inside objectId="robot1" regionId="start"/>
```

## \<settedUp/> и \<dropped/> <a href="#settedup" id="settedup"></a>

Позволяет проверить, взведено событие или нет.

#### Атрибуты

| Атрибут         | Описание                           |
| --------------- | ---------------------------------- |
| **id="event1"** | Идентификатор проверяемого события |

#### Синтаксис

```markup
<!-- Условие, что событие с id=”event1” взведено -->
<condition>
    <settedUp id="event1"/>
</condition>

<!-- Условие, что событие с id=”event2” опущено -->
<condition>
    <dropped id="event2"/>
</condition>
```

#### Пример

В условиях события “check event” проверяется, что другое событие с id=”Try move” находится во взведенном состоянии, а событие с id=”Go back” опущено и не выполняется. Если оба эти условия после проверки возвращают значение true, то программа успешно завершается.

```markup
<event id="check event" settedUpInitially="true">
    <conditions glue="and">
        <settedUp id="Try move"/>
        <dropped id="Go back"/>
    </conditions>
    <trigger>
        <success/>
    </trigger>
</event>
```

## \<timer/> <a href="#timer" id="timer"></a>

Предикат, который начинает выдавать true, когда с момента взведения данного события прошло заданное время, а до этого момента выдает false.

#### Атрибуты

| Атрибут                       | Описание                                                                                                                                                                                                                                             |
| ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **timeout="1000"**            | Промежуток времени, через которой данный предикат станет истинным. Обязательный, значение должно быть неотрицательным и целочисленным.                                                                                                               |
| **forceDropOnTimeout="true"** | Логический атрибут, позволяющий опустить событие, которое имеет в условии данный таймер. Если выставлен в true, событие будет опущено даже при наличии других активных таймеров и невыполненных условий. Опциональный. Значение по умолчанию -- true |

#### Синтаксис

```markup
<timer timeout="1000" forceDropOnTimeout="false"/>
```

#### Пример

Рассмотрим использование \<timer/> c различными значениями атрибута forceDropOnTimeout .

В событии “check region” проверяются временное и пространственное ограничения. Первое условие (timer) становится истинным спустя 1000мс, а до этого момента ложно. После этого его значение больше не изменяется. Второе условие (inside) проверяет, что робот находится в регионе с id=”start\_zone”. В тот момент, когда оба этих условия будут выполнены одновременно, программа будет выполнена успешно.

1\. Т. к. атрибут forceDropOnTimeout равен "false", то после заданного количества времени событие будет продолжать оставаться взведенным и ждать выполнения второго условия.

```markup
<event id="check region" settedUpInitially="true">
    <conditions glue="and">
        <timer timeout="1000" forceDropOnTimeout="false"/>
        <inside objectId="robot1" regionId="start_zone"/>
    </conditions>
    <trigger>
        <success/>
    </trigger>
</event>
```

2\. Т. к. атрибут forceDropOnTimeout равен "true", то после заданного количества миллисекунд событие будет опущено, несмотря на наличие .другого условия. Таким образом, если в момент времени 1000 мс робот не находится в нужном регионе, то сообщение об успешном выполнении не будет выведено даже в случае, если робот окажется там спустя некоторое время.

```markup
<event id="check region" settedUpInitially="true">
    <conditions glue="and">
        <timer timeout="1000" forceDropOnTimeout="true"/>
        <inside objectId="robot1" regionId="start_zone"/>
    </conditions>
    <trigger>
        <success/>
    </trigger>
</event>
```

## Типы переменных и арифметические операции

| Переменная                                | Описание                                                                                                                 |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| [int, double, string, bool](./#intdouble) | Целочисленная, дробная, строковая и логическая константы.                                                                |
| ****[variableValue](./#variablevalue)     | Значение переменной.                                                                                                     |
| [objectState](./#objectstate)             | Взять состояние объекта.                                                                                                 |
| [typeOf](./#typeof)                       | Взять метатип объекта с заданным идентификатором.                                                                        |
| [minus, abs](./#minusabs)                 | Унарные арифметические функции, имеют ровно 1 дочерний элемент, значение которого должно быть целочисленным.             |
| [sum, difference, min, max](./#summinmax) | Бинарные арифметические функции, имеют ровно 2 дочерних элемента, значение каждого из которых должно быть целочисленным. |

## \<int/>, \<double/>, \<string>, \<bool/> <a href="#intdouble" id="intdouble"></a>

Задание константы.

#### Атрибуты

| Атрибут       | Описание                     |
| ------------- | ---------------------------- |
| **value="0″** | Значение заданной константы. |

#### Синтаксис

```markup
<int value="0"/>

<string value="finish"/>
```

## \<variableValue/> <a href="#variablevalue" id="variablevalue"></a>

Значение переменной.&#x20;

Возможно взятие свойства какой-либо переменной, для этого используется точка. Например, значение rect.width вернет ширину прямоугольника, сохраненного в переменной rect.

#### Атрибуты

| Атрибут              | Описание       |
| -------------------- | -------------- |
| **name="my\_value"** | Имя переменной |

#### Синтаксис

```markup
<variableValue name="rotation"/>
```

## \<objectState/> <a href="#objectstate" id="objectstate"></a>

Взять состояние объекта.

#### Атрибуты

| Атрибут                                 | Описание            |
| --------------------------------------- | ------------------- |
| **object="robot1.display.labels.size"** | id взятого объекта. |

#### Синтаксис

```markup
<objectState object="robot1.display.labels.first.text"/>
```

#### Пример

```markup
<!-- Присвоим переменной rotation значение угла поворота робота -->
<setter name="rotation">
     <objectState object="robot1.rotation"/>
 </setter>
<!-- Проверяем равно ли значение переменной rotation значению угла поворота робота -->
<equals>
   <variableValue name="rotation"/>
   <objectState object="robot1.rotation"/>
</equals>
```

## \<typeOf/> <a href="#typeof" id="typeof"></a>

Взять метатип объекта с заданным идентификатором. Например: если взять `typeOf` объекта `wall` с `id=777`, то он вернет, что тип этого объекта `wall`.

Чаще всего этот элемент будет нужен для проверки типа подключенных датчиков и моторов.

#### Атрибуты

| Атрибут           | Описание                                  |
| ----------------- | ----------------------------------------- |
| **objectId="id"** | Уникальный идентификатор взятого объекта. |

#### Синтаксис

```markup
<typeOf objectId="robot1.A3"/>
```

## \<minus>..\</minus>, \<abs>...\</abs> <a href="#minusabs" id="minusabs"></a>

Унарные арифметические операции отвечающие за изменение знака и взятие модуля числа.

#### Синтаксис

```markup
<minus>
    <objectState object="robot1.rotation"/>
</minus>

<abs>
    <objectState object="robot1.rotation"/>
</abs>
```

#### Пример

```markup
<!-- Модуль разности переменной rotation и значения угла поворота робота -->
<abs>
    <difference>
        <variableValue name="rotation"/>
        <objectState object="robot1.rotation"/>
    </difference>
</abs>
```

## \<sum>, \<difference>, \<min>, \<max> <a href="#summinmax" id="summinmax"></a>

Сумма и разность значений. Минимальное и максимальное значение.

#### Пример

```markup
<!-- Разность между переменной rotation и значением угла поворота робота -->
<difference>
       <variableValue name="rotation"/>
       <objectState object="robot1.rotation"/>
</difference>

<!-- Сумма переменной counter и единицы -->
<sum>
       <variableValue name="counter"/>
       <int value="1"/>
</sum>
```

## Триггеры

| Тег                                                          | Описание                                                                                                           |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| [trigger](./#trigger)                                        | Действие или группа действий, которые будут выполнены один или множество раз по факту выполнения условия события.  |
| [fail](./#fail)                                              | Показать ошибку пользователю, завершить проверку задания.                                                          |
| [success](./#success)                                        | Показать пользователю сообщение об успешном прохождении задания и завершить проверку.                              |
| [setter](./#setter)                                          | Установить значение переменной.                                                                                    |
| [setUp, drop](./#setup)                                      | Взводит или опускает событие                                                                                       |
| [message](./#less-than-message-text-vash-tekst-greater-than) | Выводит текст                                                                                                      |

## \<trigger>...\</trigger> <a href="#trigger" id="trigger"></a>

Действие или группа действий, которые будут выполнены один или множество раз по факту выполнения условия события.&#x20;

#### Синтаксис

```markup
<trigger>
	<success/>
</trigger>
```

## \<fail/> <a href="#fail" id="fail"></a>

Показать ошибку, завершить проверку задания.

#### Атрибуты

| Атрибут                       | Описание                |
| ----------------------------- | ----------------------- |
| **message="Неверный ответ!"** | текст выведенной ошибки |

#### Синтаксис

```markup
<fail message="Неверный ответ!"/>
```

## \<success/> <a href="#success" id="success"></a>

Задание успешно пройдено.

#### Атрибуты

| Атрибут          | Описание                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| deffered="false" |  Опциональный. По умолчанию равен "false". При выставлении его в _true_ данный триггер не остановит выполнение программы, т. е. чекер дождется конца программы и, либо скажет, что программа выполнена успешно, если ошибок не было, либо выпадет с ошибкой в противном случае. Другими словами атрибут _deferred_  не позволяет получить ошибку "Программа закончилась, но задание не выполнено": программа либо завершится с успехом, либо с содержательной ошибкой типа "Превышен лимит времени". |

#### Синтаксис

```markup
<success/>
```

## \<setter>...\</setter> <a href="#setter" id="setter"></a>

Установить значение переменной

#### Атрибуты

| Атрибут          | Описание            |
| ---------------- | ------------------- |
| name="my\_value" | Название переменной |

#### Пример

```markup
<!-- Создаем переменную total_score со значением 0.-->
<setter name="total_score">
       <int value="0"/>
 </setter>

<!-- Добавляем к переменной total_score + 2. -->
<setter name="total_score">
       <sum>
              <variableValue name="total_score"/>
              <int value="2"/>
       </sum>
</setter>
```

## \<setUp/>, \<drop/> <a href="#setup" id="setup"></a>

Взводит или опускает событие

#### Атрибуты

| Атрибут                 | Описание              |
| ----------------------- | --------------------- |
| **id="finish checker"** | id выбранного события |

#### Пример

```markup
<!-- Запустить событие "finish checker" -->
<triggers>
				<setUp id="finish checker"/>
</triggers>
```

## \<message/>&#x20;

Выводит текст в консоль

**Атрибуты**

| Атрибут              | Описание          |
| -------------------- | ----------------- |
| text="Hello, world!" | Необходимый текст |
|                      |                   |

```javascript
<trigger>
<message text="Hello, world!"/>
</trigger>

При срабатывании такого триггера в консоль робота будет выведен текст "Hello, world!"
```

## Названия датчиков

#### Датчики для робота TRIK

| Название                                       | Описание            |
| ---------------------------------------------- | ------------------- |
| twoDModel::robotModel::parts::RangeSensor      | Датчик расстояния   |
| trik::robotModel::twoD::parts::TwoDLightSensor | Датчик освещенности |
| twoDModel::robotModel::parts::TouchSensor      | Датчик касания      |
| trik::robotModel::twoD::parts::LineSensor      | Датчик линии        |

#### Датчики для робота Lego EV3

| Название                                         | Описание                      |
| ------------------------------------------------ | ----------------------------- |
| twoDModel::robotModel::parts::RangeSensor        | Датчик расстояния             |
| twoDModel::robotModel::parts::LightSensor        | Датчик освещённости           |
| twoDModel::robotModel::parts::TouchSensor        | Датчик касания                |
| twoDModel::robotModel::parts::ColorSensorRed     | Датчик цвета (красный)        |
| twoDModel::robotModel::parts::ColorSensorGreen   | Датчик цвета (зеленый)        |
| twoDModel::robotModel::parts::ColorSensorBlue    | Датчик цвета (синий)          |
| twoDModel::robotModel::parts::ColorSensorPassive | Датчик цвета (пассивный)      |
| twoDModel::robotModel::parts::ColorSensorFull    | Датчик цвета EVX/NXT (цвет)   |
| twoDModel::robotModel::parts::ColorSensorAmbient | Датчик цвета EV3 (рассеянный) |
| ev3::robotModel::twoD::parts::GyroscopeSensor    | Гиродатчик                    |
| ev3::robotModel::twoD::parts::GyroscopeSensor    | Компас                        |

## Дополнительные свойства робота

| Свойство                | Описание                                                                                                |
| ----------------------- | ------------------------------------------------------------------------------------------------------- |
| robot1.rotation         | Позволяет узнать текущий угол поворота робота                                                           |
| robot1.x и robot1.y     | Позволяет узнать координаты робота                                                                      |
| robot1.led.color        | Позволяет узнать цвет диода                                                                             |
| robot1.marker.isDown    | Проверяет, что у робота установлен маркер и он рисует линию на поле. Возвращает значения true или false |
| robot1.shell.lastPhrase | Узнать текст, который сказал робот                                                                      |

## Работа с экраном контроллера

| Свойство                         | Описание                                                                                              |
| -------------------------------- | ----------------------------------------------------------------------------------------------------- |
| robot1.display.sadSmiles         | Проверяет, что на экране контроллера установлен грустный смайлик. Возвращает значение true или false. |
| robot1.display.smiles            | Проверяет, что на экране контроллера установлен веселый смайлик. Возвращает значение true или false.  |
| robot1.display.labels.first.text | Текст сообщения (label), которое было выведено на экран первым.                                       |
| robot1.display.labels.last.text  | Тест сообщения (label), которое было выведено на экран последним.                                     |
| robot1.display.labels.size       | Узнать количество label-ов, выведенных на экран.                                                      |

#### Пример

Проверяем, что на экран контроллера было выведено слово “сообщение”. Регистр слова важен.

```markup
<equals>
        <objectState object="robot1.display.labels.first.text"/>
        <string value="сообщение"/>
</equals>
```

## Пример добавления ограничений

Стартовав в синем квадрате, необходимо проехать вдоль стены с помощью датчика расстояния ИК до красного квадрата.

![](https://thumb.tildacdn.com/tild6265-3339-4037-b064-366561643230/-/resize/740x/-/format/webp/2019-04-03\_12-46-00.png)

```markup
<?xml version="1.0" encoding="UTF-8"?>
<root>
   <world>
      <background />
      <walls>
         <!-- Стена -->
         <wall id="{wall1}" end="300:150" begin="0:100" />
         <wall id="{wall2}" end="550:100" begin="300:150" />
         <wall id="{wall3}" end="650:200" begin="550:100" />
         <wall id="{wall4}" end="850:300" begin="650:200" />
         <wall id="{wall5}" end="1200:300" begin="850:300" />
         <wall id="{wall6}" end="1600:50" begin="1200:300" />
      </walls>
      <skittles />
      <balls />
      <colorFields />
      <images />
      <regions>
         <!-- Регионы -->
         <region visible="true" id="finish" x="1300" color="#ff0000" text="Finish" type="rectangle" width="300" textX="0" textY="0" y="-200" filled="true" height="300" />
         <region visible="true" id="start_zone" x="-50" color="#0000ff" text="Start" type="rectangle" width="150" textX="0" textY="0" y="100" filled="true" height="-150" />
         <region visible="false" id="warzone_1" x="-50" color="#ffff00" text="warzone1" type="rectangle" width="650" textX="0" textY="0" y="-50" filled="true" height="200" />
         <region visible="false" id="warzone_2" x="600" color="#ffff00" text="warzone2" type="rectangle" width="250" textX="0" textY="0" y="0" filled="true" height="250" />
         <region visible="false" id="warzone_3" x="850" color="#ffff00" text="warzone3" type="rectangle" width="750" textX="0" textY="0" y="50" filled="true" height="250" />
      </regions>
   </world>
   <robots>
      <!-- Описание робота -->
      <robot id="trikKitRobot" position="0:0" direction="0">
         <sensors>
            <sensor port="A1###input###А1###sensorA1" position="75:25" type="trik::robotModel::parts::TrikInfraredSensor" direction="45" />
            <sensor port="M3###output###JM3$$$C$$$3###" position="75:25" type="kitBase::robotModel::robotParts::Motor" direction="0" />
            <sensor port="M4###output###JM4$$$D$$$4###" position="75:25" type="kitBase::robotModel::robotParts::Motor" direction="0" />
         </sensors>
         <startPosition id="{ee2c46c1-23fc-4cda-98f4-77d9de775305}" x="25" y="25" direction="0" />
         <wheels left="M3###output###М3###" right="M4###output###М4###" />
      </robot>
   </robots>
   <constraints>
      <!-- Лимит на выполнение программы (30 секунд) -->
      <timelimit value="30000" />
      <!-- Зональное ограничение на начало езды. Проверяется один раз в начале программы -->
      <constraint checkOnce="true" failMessage="Робот должен находиться в синем квадрате перед запуском!">
         <inside regionId="start_zone" objectId="robot1" />
      </constraint>
      <!-- Ограничение на наличие и тип датчиков -->
      <constraint checkOnce="true" failMessage="Должен быть подключен только Датчик расстояния ИК на A1">
         <conditions glue="and">
            <equals>
               <typeOf objectId="robot1.A1" />
               <string value="trik::twoDModel::robotModel::parts::RangeSensor" />
            </equals>
            <equals>
               <typeOf objectId="robot1.A2" />
               <string value="undefined" />
            </equals>
            <equals>
               <typeOf objectId="robot1.A3" />
               <string value="undefined" />
            </equals>
            <equals>
               <typeOf objectId="robot1.A4" />
               <string value="undefined" />
            </equals>
            <equals>
               <typeOf objectId="robot1.A5" />
               <string value="undefined" />
            </equals>
            <equals>
               <typeOf objectId="robot1.A6" />
               <string value="undefined" />
            </equals>
            <equals>
               <typeOf objectId="robot1.D1" />
               <string value="undefined" />
            </equals>
            <equals>
               <typeOf objectId="robot1.D2" />
               <string value="undefined" />
            </equals>
         </conditions>
      </constraint>
      <!-- Контроль езды робота -->
      <constraint failMessage="Робот попытался выехать из разрешенной зоны!">
         <conditions glue="or">
            <inside regionId="warzone_1" objectId="robot1" />
            <inside regionId="warzone_2" objectId="robot1" />
            <inside regionId="warzone_3" objectId="robot1" />
         </conditions>
      </constraint>
      <!-- Событие, проверяющее не заехал ли робот в зону финиша -->
      <event settedUpInitially="true">
         <condition>
            <timer timeout="100" forceDropOnTimeout="true" />
         </condition>
         <trigger>
            <setUp id="finish checker" />
         </trigger>
      </event>
      <!-- Событие, оповещающее об успешном выполнении программы -->
      <event id="finish checker" settedUpInitially="false">
         <condition>
            <inside regionId="finish" objectId="robot1" />
         </condition>
         <trigger>
            <success />
         </trigger>
      </event>
   </constraints>
</root>

```
