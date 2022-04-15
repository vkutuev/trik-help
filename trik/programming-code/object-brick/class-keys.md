# Класс «keys»

Служит для работы с кнопками на пульте робота.

| Метод                                        | Описание                                                                                             |
| -------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| [buttonPressed](class-keys.md#buttonpressed) | Посылается, когда кнопка с указанным кодом нажата или отпущена.                                      |
| [isPressed](class-keys.md#ispressed)         | Возвращает true, если кнопка с указанным кодом нажата в данный момент.                               |
| [reset](class-keys.md#reset)                 | Сбрасывает запомненные нажатия кнопок.                                                               |
| [wasPressed](class-keys.md#waspressed)       | Возвращает, была ли нажата кнопка с указанным кодом, сбрасывает запомненные нажатия для этой кнопки. |

## buttonPressed

Посылается, когда кнопка с указанным кодом нажата или отпущена.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.keys().buttonPressed.connect(lambda code, value: brick.stop() if code == KeysEnum.Up else print(code))
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.keys().buttonPressed.connect(function(code, value){if (code==KeysEnum.Up)brick.stop() ; });
```
{% endtab %}
{% endtabs %}

Первый параметр — код кнопки, второй — 1, если кнопка нажата, 0, если отпущена.

## isPressed

Возвращает `true`, если кнопка с указанным кодом нажата в данный момент.\
Возможные варианты:

* `KeysEnum.Left` (код 105),
* `KeysEnum.Up` (код 103),
* `KeysEnum.Down` (код 108),
* `KeysEnum.Enter` (код 28),
* `KeysEnum.Right` (код 106),
* `KeysEnum.Power` (код 116),
* `KeysEnum.Esc` (код 1).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.keys().isPressed(KeysEnum.Up)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.keys().isPressed(KeysEnum.Up);
```
{% endtab %}
{% endtabs %}

## reset

Сбрасывает запомненные нажатия кнопок.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
brick.keys().reset()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.keys().reset();
```
{% endtab %}
{% endtabs %}

## wasPressed

Возвращает, была ли нажата кнопка с указанным кодом, сбрасывает запомненные нажатия для этой кнопки.\
Возможные варианты:

* `KeysEnum.Left` (код 105),
* `KeysEnum.Up` (код 103),
* `KeysEnum.Down` (код 108),
* `KeysEnum.Enter` (код 28),
* `KeysEnum.Right` (код 106),
* `KeysEnum.Power` (код 116),
* `KeysEnum.Esc` (код 1).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
brick.keys().wasPressed(KeysEnum.Up)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.keys().wasPressed(KeysEnum.Up);
```
{% endtab %}
{% endtabs %}
