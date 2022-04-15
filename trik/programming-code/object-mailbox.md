# Объект «mailbox»

Реализует связь между роботами в сети посредством механизма почтовых ящиков.

| Метод                                          | Описание                                                                                                                                                             |
| ---------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [connect](object-mailbox.md#connect)           | Подключается к роботу с заданным IP-адресом по заданному порту (или порту по умолчанию), сообщает ему свой бортовой номер и регистрируется в сети «почтовых ящиков». |
| [hasMessages](object-mailbox.md#hasmessages)   | Возвращает **`true`**, если роботу пришло новое сообщение.                                                                                                           |
| [myHullNumber](object-mailbox.md#myhullnumber) | Возвращает бортовой номер робота.                                                                                                                                    |
| [newMessage](object-mailbox.md#newmessage)     | Посылает сообщение после получения сообщения.                                                                                                                        |
| [receive](object-mailbox.md#receive)           | Получает новое сообщение или блокирует исполнение скрипта до тех пор, пока сообщение не придёт.                                                                      |
| [send](object-mailbox.md#send)                 | Посылает роботу с указанным бортовым номером (или всем роботам) указанное сообщение.                                                                                 |

## connect

Подключается к роботу с заданным IP-адресом по заданному порту (или порту по умолчанию), сообщает ему свой бортовой номер и регистрируется в сети «почтовых ящиков».

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
mailbox.connect("ipAddress")
mailbox.connect("ipAddress", port)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
mailbox.connect("ipAddress");
mailbox.connect("ipAddress", port);
```
{% endtab %}
{% endtabs %}

В качестве параметров необходимо указать IP-адрес робота и порт. В случае, если порт не указан, используется порт по умолчанию.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
mailbox.connect("192.168.0.20", 8889)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
mailbox.connect("192.168.0.20", 8889);
```
{% endtab %}
{% endtabs %}

## hasMessages

Возвращает `true`, если роботу пришло новое сообщение.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
mailbox.hasMessages()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
mailbox.hasMessages();
```
{% endtab %}
{% endtabs %}

## myHullNumber

Возвращает бортовой номер робота.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
x = mailbox.myHullNumber()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var x = mailbox.myHullNumber();
```
{% endtab %}
{% endtabs %}

## newMessage

Посылает сообщение после получения нового сообщения.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
mailbox.newMessage.connect(lambda sender, message: print(message))
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
mailbox.newMessage.connect(function(sender, message) { print(message); });
```
{% endtab %}
{% endtabs %}

Первый параметр — бортовой номер отправителя, второй — само сообщение.

## receive

Получает новое сообщение или блокирует исполнение скрипта до тех пор, пока сообщение не придёт.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
message = mailbox.receive()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var message = mailbox.receive();	
```
{% endtab %}
{% endtabs %}

## send

Посылает роботу с указанным бортовым номером (или всем роботам) указанное сообщение.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
mailbox.send("message")
mailbox.send(boardNumber, "message")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
mailbox.send("message");
mailbox.send(boardNumber, "message");
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать бортовой номер робота, которому хотите послать сообщение и сообщение. Если бортовой номер не указан, то сообщение отправляется всем роботам, зарегистрированным в сети.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
mailbox.send(1, "Hello") # отправка сообщения роботу с бортовым номер 1
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
mailbox.send(1, "Hello"); // отправка сообщения роботу с бортовым номер 1
```
{% endtab %}
{% endtabs %}
