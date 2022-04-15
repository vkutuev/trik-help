# Класс «motor»

Предоставляет управление мотором робота (силовым или сервомотором), подключающимся к портам M1, …, M4, S1, ..., S6.

| Метод                               | Описание                                                        |
| ----------------------------------- | --------------------------------------------------------------- |
| [brake](class-motor.md#brake)       | Блокировка моторов для торможения в течение указанного времени. |
| [power](class-motor.md#power)       | Возвращает текущую мощность мотора.                             |
| [powerOff](class-motor.md#poweroff) | Выключает мотор.                                                |
| [setPower](class-motor.md#setpower) | Включает мотор с указанной мощностью.                           |

## brake

Блокировка моторов для торможения в течение указанного времени в миллисекундах.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.motor(motorName).brake(durationMs)
brick.motor("motorName").brake(durationMs)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.motor(motorName).brake(durationMs);
brick.motor("motorName").brake(durationMs);
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать время в миллисекундах.

## power

Возвращает текущую мощность мотора (от -100 до 100).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
pow1 = brick.motor(motorName).power()
pow2 = brick.motor("motorName").power()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var pow1 = brick.motor(motorName).power();
var pow2 = brick.motor("motorName").power();
```
{% endtab %}
{% endtabs %}

## powerOff

Выключает мотор.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.motor(motorName).powerOff()
brick.motor("motorName").powerOff()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.motor(motorName).powerOff();
brick.motor("motorName").powerOff();
```
{% endtab %}
{% endtabs %}

## setPower

Включает мотор с указанной мощностью.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.motor(motorName).setPower(power)
brick.motor("motorName").setPower(power)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.motor(motorName).setPower(power);
brick.motor("motorName").setPower(power);
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать мощность.Мощность задаётся в диапазоне от -100 («полный назад») до 100 («полный вперёд»). 0 соответствует `force break`, то есть мотор останавливается, при этом он заблокирован и остаётся под напряжением.
