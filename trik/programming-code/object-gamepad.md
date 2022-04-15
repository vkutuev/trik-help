# Объект «gamepad»

Служит для работы с программируемым пультом управления «[TRIK Gamepad](../../gamepad/about/)».

| Метод                                                  | Описание                                                                                                             |
| ------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------- |
| [buttonWasPressed](object-gamepad.md#buttonwaspressed) | Возвращает `true`, если на пульте была нажата кнопка с указанным номером.                                            |
| [isPadPressed](object-gamepad.md#ispadpressed)         | Возвращает, нажата ли в данный момент область управления на пульте.                                                  |
| [padX](object-gamepad.md#padx)                         | Если указанная область управления на пульте нажата, возвращает текущую координату нажатия по оси X.                  |
| [padY](object-gamepad.md#pady)                         | Если указанная область управления на пульте нажата, возвращает текущую координату нажатия по оси Y.                  |
| [padUp](object-gamepad.md#padup)                       | Посылается, когда пользователь оторвал палец от области управления с указанным номером.                              |
| [reset](object-gamepad.md#reset)                       | Сбрасывает запомненные события от пульта.                                                                            |
| [wheel](object-gamepad.md#wheel)                       | Если на пульте включён «руль» (события от акселерометра устройства), возвращает текущий наклон пульта.               |
| [wheelEvent](object-gamepad.md#wheelevent)             | Посылается, когда на пульте включён «руль» (события от акселерометра устройства) и пользователь повернул устройство. |

| Сигнал                                     | Описание                                                                                          |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| [button](object-gamepad.md#button)         | Посылается, когда пользователь нажал на одну из пяти кнопок внизу пульта.                         |
| [connected](object-gamepad.md#connected)   | Посылается при подключении пульта к роботу.                                                       |
| [disconnect](object-gamepad.md#disconnect) | Посылается при отключении пульта.                                                                 |
| [pad](object-gamepad.md#pad)               | Посылается, когда пользователь нажал на область управления на пульте или переместил палец по ней. |

## button

Посылается, когда пользователь нажал на одну из пяти кнопок внизу пульта.

## buttonWasPressed

Возвращает `true`, если на пульте была нажата кнопка с указанным номером. Сбрасывает запомненное нажатие для этой кнопки.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
gamepad.buttonWasPressed(buttonNumber)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
gamepad.buttonWasPressed(buttonNumber);
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать номер кнопки — от 1 до 5.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
gamepad.buttonWasPressed(5)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
gamepad.buttonWasPressed(5);
```
{% endtab %}
{% endtabs %}

## connected

Посылается при подключении пульта к роботу.

## disconnect

Посылается при отключении пульта.

## isPadPressed

Возвращает, нажата ли в данный момент область управления на пульте. Области управления имеют номера 0 и 1.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
gamepad.isPadPressed(padId)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
gamepad.isPadPressed(padId);
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать номер области управления — 0 или 1.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
gamepad.isPadPressed(1)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
gamepad.isPadPressed(1);
```
{% endtab %}
{% endtabs %}

## pad

Посылается, когда пользователь нажал на область управления на пульте или переместил палец по ней.

## padX

Если указанная область управления на пульте нажата, возвращает текущую x-координату нажатия.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
gamepad.padX(padId)
```
{% endtab %}

{% tab title="JavaScript" %}
```
gamepad.padX(padId);
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать — номер области управления `padId`_._

## padY

Если указанная область управления на пульте нажата, возвращает текущую y-координату нажатия.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
gamepad.padY(padId)
```
{% endtab %}

{% tab title="JavaScript" %}
```
gamepad.padY(padId);
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать — номер области управления `padId`_._

## padUp

Посылается, когда пользователь оторвал палец от области управления с указанным номером.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
gamepad.padUp.connect(lambda padId, x, y: brick.stop())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
gamepad.padUp.connect( function(padId, x, y) { brick.stop(); });
```
{% endtab %}
{% endtabs %}

В качестве параметров необходимо указать:

* `padId` — номер области управления.
* `x`, `y` — координаты последнего известного нажатия от -100 до 100. Координата (-100, -100) соответствует левому верхнему углу области управления.

## reset

Сбрасывает запомненные события от пульта.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
gamepad.reset()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
gamepad.reset();
```
{% endtab %}
{% endtabs %}

## wheel

Если на пульте включён «руль» (события от акселерометра устройства), возвращает текущий наклон пульта.

Наклон кодируется числом от -100 до 100, -100 соответствует крайнему левому положению «руля», 100 — крайнему правому.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
gamepad.wheel()
```
{% endtab %}

{% tab title="JavaScript" %}
```
gamepad.wheel();
```
{% endtab %}
{% endtabs %}

## wheelEvent

Посылается, когда на пульте включён «руль» (события от акселерометра устройства) и пользователь повернул устройство.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
gamepad.wheelEvent.connect(lambda percent: brick.motor("E1").setPower(percent))
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
gamepad.wheelEvent.connect(function(percent) { brick.motor("E1").setPower(percent); });
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать число от -100 до 100, -100 соответствует крайнему левому положению «руля», 100 — крайнему правому.
