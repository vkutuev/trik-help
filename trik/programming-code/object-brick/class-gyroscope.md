# Класс «gyroscope»

Представляет [гироскоп](./#gyroscope) контроллера ТРИК. В состоянии покоя среднее значение выходного сигнала гироскопа не равно нулю и называется **смещением нуля** (`bias`) или **систематической ошибкой** (`bias error`).

Параметр обусловлен многими факторами и может изменяться, например, в зависимости от окружающей температуры.

Для правильной работы гироскопа необходимо вычитать смещение нуля из приходящих значений. Вычислить его можно с помощью метода «[calibrate](class-gyroscope.md#calibrate)».

Так как калибровка занимает длительное время, то при частом запуске модели можно выполнять ее один раз, после чего запоминать значение в переменную с помощью «[getCalibrationVaules»](class-gyroscope.md#getcalibrationvalues), а при запуске программы вместо калибровки вызывать «[setCalibrationValues](class-gyroscope.md#setcalibrationvalues)».

| Метод                                                           | Описание                                                                                                                          |
| --------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| [calibrate](class-gyroscope.md#calibrate)                       | Вычисляет смещением нуля в течение указанного времени и инициализирует гироскоп этим параметром, сбрасывает текущие углы наклона. |
| [getCalibrationValues](class-gyroscope.md#getcalibrationvalues) | Возвращает объект, в котором содержатся необходимые данные о смещении нуля.                                                       |
| [isCalibrated](class-gyroscope.md#iscalibrated)                 | Возвращает true в случае завершении калибровки, false — в противном случае.                                                       |
| [read](class-gyroscope.md#read)                                 | Возвращает массив из семи элементов: угловые скорости по трем осям, время последнего замера, углы наклона по трем осям.           |
| [readRawData](class-gyroscope.md#readrawdata)                   | Возвращает массив из трех элементов с угловыми скоростями по трем осям.                                                           |
| [setCalibrationValues](class-gyroscope.md#setcalibrationvalues) | Устанавливает объект, содержащий необходимые параметры о смещении нуля.                                                           |

| Сигнал                                                        | Описание                                                       |
| ------------------------------------------------------------- | -------------------------------------------------------------- |
| [calibrationFinished](class-gyroscope.md#calibrationfinished) | Сигнал, посылаемый сенсором после окончания калибровки.        |
| [newData](class-gyroscope.md#newdata)                         | Сигнал, посылаемый сенсором, когда у него готовы новые данные. |

## calibrate

Вычисляет смещение нуля в течение указанного времени и инициализирует гироскоп этим параметром, сбрасывает текущие углы наклона.Рекомендуемое время калибровки — 10−20 секунд.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
brick.gyroscope().calibrate(msec)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.gyroscope().calibrate(msec);
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать:

* `msec` — время в миллисекундах.

## calibrationFinished

Сигнал, посылаемый сенсором после окончания калибровки.

## getCalibrationValues

Возвращает объект, в котором содержатся необходимые данные о смещении нуля.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
brick.gyroscope().getCalibrationValues()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.gyroscope().getCalibrationValues();
```
{% endtab %}
{% endtabs %}

## isCalibrated

Возвращает `true` в случае завершении калибровки, `false` — в противном случае.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
brick.gyroscope().isCalibrated()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.gyroscope().isCalibrated();
```
{% endtab %}
{% endtabs %}

## newData

Сигнал, посылаемый сенсором, когда у него готовы новые данные.

## read

Возвращает массив из семи элементов:

* 0−2 — угловые скорости по трем осям (в миллиградусах/секунды),
* 3 — время последнего замера (в микросекундах),
* 4−6 — углы наклона по трем осям (в миллиградусах).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
brick.gyroscope().read()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.gyroscope().read();
```
{% endtab %}
{% endtabs %}

## readRawData

Возвращает массив из трех элементов с угловыми скоростями по трем осям.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
brick.gyroscope().readRawData()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.gyroscope().readRawData();
```
{% endtab %}
{% endtabs %}

## setCalibrationValues

Устанавливает объект, содержащий необходимые параметры о смещении нуля.&#x20;

{% hint style="warning" %}
Так как калибровка занимает длительное время, то при частом запуске модели можно выполнять ее один раз, после чего запоминать значение в переменную с помощью «[getCalibrationVaules](class-gyroscope.md#getcalibrationvalues)», а при запуске программы вместо калибровки вызывать «setCalibrationValues».
{% endhint %}

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
brick.gyroscope().setCalibrationValues(values)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.gyroscope().setCalibrationValues(values);
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать:

* `values` — объект, содержащий данные о биасе.
