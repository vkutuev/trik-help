# Класс «marker»

Предоставляет доступ к рисованию маркером заданного цвета на полу. Доступен только в режиме 2D модели.

| Метод                              | Описание                                                                                                                                                                                      |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [down](class-marker.md#down)       | Начать рисование маркером заданного цвета на полу. При движении робота в двумерной модели за ним будет оставаться цветная линия. Если был установлен маркер другого цвета, он будет заменен.  |
| [up](class-marker.md#up)           | Закончить рисование маркером.                                                                                                                                                                 |
| [isDown](class-marker.md#isdown)   | Возвращает `true`, если маркер активен, `false`- если нет.                                                                                                                                    |
| [setDown](class-marker.md#setdown) | Вызывает метод `down("black")`, или `up()` в зависимости от аргумента.                                                                                                                        |

## down

Начать рисование маркером заданного цвета на полу. При движении робота в двумерной модели за ним будет оставаться цветная линия. Если был установлен маркер другого цвета, он будет заменен.&#x20;

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.marker().down(color)
brick.marker().down("color")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.marker().down(color)
brick.marker().down("color")
```
{% endtab %}
{% endtabs %}

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.marker().down("blue")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.marker().down("blue")
```
{% endtab %}
{% endtabs %}

## up

Закончить рисование маркером.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.marker().up()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.marker().up()
```
{% endtab %}
{% endtabs %}

## isDown

Возвращает `true`, если маркер активен, `false`- если нет.&#x20;

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.marker().isDown()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.marker().isDown();
```
{% endtab %}
{% endtabs %}

## setDown

Вызывает метод `down("black")`, или `up()` в зависимости от аргумента.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.marker().setDown(True) # Вызывает brick.marker().down("black")
brick.marker().setDown(False) # Вызывает brick.marker().up()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.marker().setDown(true) // Вызывает brick.marker().down("black")
brick.marker().setDown(false) // Вызывает brick.marker().up()
```
{% endtab %}
{% endtabs %}

