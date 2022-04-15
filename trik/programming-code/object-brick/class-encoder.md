# Класс «encoder»

Представляет энкодеры силовых моторов, подключающиеся к портам E1, E2, E3, E4.

| Метод                                       | Описание                                                            |
| ------------------------------------------- | ------------------------------------------------------------------- |
| [read](class-encoder.md#read)               | Возвращает текущее показание энкодера в градусах на заданном порту. |
| [reset](class-encoder.md#reset)             | Сбрасывает на 0 текущее показание энкодера.                         |
| [readRawData](class-encoder.md#readrawdata) | Возвращает текущее показание энкодера в «тиках» на заданном порту.  |

## read

Возвращает текущее показание энкодера в градусах на заданном порту.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.encoder(portName).read()
brick.encoder("portName").read()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.encoder(portName).read();
brick.encoder("portName").read();
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать порт.

#### Примеры

{% tabs %}
{% tab title="Python" %}
```python
brick.encoder(E1).read()
brick.encoder("E2").read()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.encoder(E1).read();
brick.encoder("E2").read();
```
{% endtab %}
{% endtabs %}

## reset

Сбрасывает в 0 текущее показание энкодера.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.encoder(portName).reset()
brick.encoder("portName").reset()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.encoder(portName).reset();
brick.encoder("portName").reset();
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать порт.

#### Примеры

{% tabs %}
{% tab title="Python" %}
```python
brick.encoder(E1).reset()
brick.encoder("E2").reset()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.encoder(E1).reset();
brick.encoder("E2").reset();
```
{% endtab %}
{% endtabs %}

## readRawData

Возвращает текущее показание энкодера в «тиках» на заданном порту.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.encoder(portName).readRawData()
brick.encoder("portName").readRawData()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.encoder(portName).readRawData();
brick.encoder("portName").readRawData();
```
{% endtab %}
{% endtabs %}

#### Примеры

{% tabs %}
{% tab title="Python" %}
```python
brick.encoder(E1).readRawData()
brick.encoder("E2").readRawData()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.encoder(E1).readRawData();
brick.encoder("E2").readRawData();
```
{% endtab %}
{% endtabs %}
