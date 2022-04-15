# Класс «sensor»

—Представляет сенсор (аналоговый или цифровой), подключающийся к портам A1, …, A6, D1, D2.

| Метод                                      | Описание                                                                                                 |
| ------------------------------------------ | -------------------------------------------------------------------------------------------------------- |
| [read](class-sensor.md#read)               | Возвращает текущее показание сенсора (цифрового или аналогового), подключённого к данному порту.         |
| [readRawData](class-sensor.md#readrawdata) | Возвращает текущее «сырое» показание сенсора (цифрового или аналогового), подключённого к данному порту. |

## read

Возвращает текущее показание сенсора (цифрового или аналогового), подключённого к данному порту. Возвращается приведённое значение, зависящее от конфигурации порта, которая описывается в файле `model-config.xml` в папке `trik` на роботе.

Например, ИК-датчик расстояния возвращает значение в сантиметрах.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
data1 = brick.sensor(sensorName).read()
data2 = brick.sensor("sensorName").read()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var data1 = brick.sensor(sensorName).read();
var data2 = brick.sensor("sensorName").read();
```
{% endtab %}
{% endtabs %}

## readRawData

Возвращает текущее «сырое» показание сенсора (цифрового или аналогового), подключённого к данному порту. Диапазон значений зависит от конкретного сенсора и не учитывает конфигурацию робота (возвращаются физические показания сенсора, например, задержка принятого ультразвукового сигнала).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
data1 = brick.sensor(sensorName).readRawData()
data2 = brick.sensor("sensorName").readRawData()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var data1 = brick.sensor(sensorName).readRawData();
var data2 = brick.sensor("sensorName").readRawData();
```
{% endtab %}
{% endtabs %}
