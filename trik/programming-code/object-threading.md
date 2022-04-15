# Объект «Threading»

Предоставляет управление параллельными потоками.

| Метод                                                | Описание                                                              |
| ---------------------------------------------------- | --------------------------------------------------------------------- |
| [joinThread](object-threading.md#jointhread)         | Ожидает завершения указанного потока.                                 |
| [killThread](object-threading.md#killthread)         | Заканчивает исполнение указанного потока.                             |
| [receiveMessage](object-threading.md#receivemessage) | Запрашивает принятое сообщение.                                       |
| [sendMessage](object-threading.md#sendmessage)       | Посылает сообщение указанному потоку.                                 |
| [startThread](object-threading.md#startthread)       | Запускает переданную в качестве параметра функцию в отдельном потоке. |

## joinThread

Ожидает завершения указанного потока.

#### Синтаксис

{% tabs %}
{% tab title="JavaScript" %}
```javascript
Threading.joinThread("threadId")
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать id потока.

## killThread

Заканчивает исполнение указанного потока.

#### Синтаксис

{% tabs %}
{% tab title="JavaScript" %}
```javascript
Threading.killThread("threadId")
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать id потока.

## receiveMessage

Запрашивает принятое сообщение.

#### Синтаксис

{% tabs %}
{% tab title="JavaScript" %}
```javascript
Threading.receiveMessage(wait)
```
{% endtab %}
{% endtabs %}

Если `wait` равен `true`, то ожидает, пока не придет сообщение.

## sendMessage

Посылает сообщение указанному потоку.

#### Синтаксис

{% tabs %}
{% tab title="JavaScript" %}
```javascript
Threading.sendMessage("threadId", "message")
```
{% endtab %}
{% endtabs %}

В качестве параметров необходимо указать id потока и сообщение.

## startThread

Запускает переданную в качестве параметра функцию в отдельном потоке.

{% hint style="warning" %}
**Внимание!** При этом создаётся новая копия для всех глобальных переменных. Так что если в одном потоке значение переменной меняется, в другом потоке оно остаётся старым.
{% endhint %}

#### Синтаксис

{% tabs %}
{% tab title="JavaScript" %}
```javascript
Threading.startThread("newThreadId", "functionName")
```
{% endtab %}
{% endtabs %}

В качестве параметров необходимо указать id потока и функцию.
