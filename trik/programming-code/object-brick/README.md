# Объект «brick»

Объект «brick» представляет контроллер ТРИК и предоставляет доступ к устройствам робота.

| Метод                             | Описание                                                                                                      |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| [accelerometer](./#accelerometer) | Предоставляет доступ к акселерометру.                                                                         |
| [battery](./#battery)             | Предоставляет доступ к информации об аккумуляторе.                                                            |
| [colorSensor](./#colorsensor)     | Предоставляет доступ к датчику цвета по видеокамере.                                                          |
| [display](./#display)             | Предоставляет доступ к дисплею робота.                                                                        |
| [encoder](./#encoder)             | Предоставляет доступ к энкодеру на указанном порту.                                                           |
| [getStillImage](./#getstillimage) | Получить фотографию с камеры в виде массива байт.                                                             |
| [gyroscope](./#gyroscope)         | Предоставляет доступ к гироскопу.                                                                             |
| [keys](./#keys)                   | Предоставляет доступ к кнопкам на корпусе робота.                                                             |
| [playSound](./#playsound)         | Проиграть звуковой файл.                                                                                      |
| [playTone](./#playtone)           | Проиграть звук с заданной частотой.                                                                           |
| [led](./#led)                     | Предоставляет доступ к светодиоду на корпусе робота.                                                          |
| [lineSensor](./#linesensor)       | Предоставляет доступ к датчику линии по видеокамере.                                                          |
| [motor](./#motor)                 | Предоставляет доступ к мотору на указанном порту.                                                             |
| [objectSensor](./#objectsensor)   | Предоставляет доступ к датчику объекта по видеокамере.                                                        |
| [say](./#say)                     | Произнести переданную как параметр строку (на русском или английском языке).                                  |
| [sensor](./#sensor)               | Предоставляет доступ к сенсору на указанном порту.                                                            |
| [stop](./#stop)                   | Останавливает все моторы и активные датчики, убирает нарисованное на дисплее.                                 |
| [marker](./#marker)               | Предоставляет доступ к рисованию маркером заданного цвета на полу. Доступен только в режиме двумерной модели. |

## accelerometer

Предоставляет доступ к акселерометру (класс «[Accelerometer](class-accelerometer.md)»).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.accelerometer();
```
{% endtab %}

{% tab title="JavaScript " %}
```javascript
brick.accelerometer();
```
{% endtab %}
{% endtabs %}

## battery

Предоставляет доступ к информации об аккумуляторе.(класс «[Battery](class-battery.md)»).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.battery();
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.battery();
```
{% endtab %}
{% endtabs %}

## colorSensor

Предоставляет доступ к датчику цвета по видеокамере (класс «[ColorSensor](class-colorsensor.md)»).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.colorSensor("video1")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.colorSensor("video1");
```
{% endtab %}
{% endtabs %}

## display

Предоставляет доступ к дисплею робота (класс «[Display](class-display.md)»).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
brick.display()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display();
```
{% endtab %}
{% endtabs %}

## encoder

Предоставляет доступ к энкодеру на указанном порту (класс «[Encoder](class-encoder.md)»).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.encoder(portName)
brick.encoder("portName")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.encoder(portName);
brick.encoder("portName");
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать порт.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.encoder(E1) # вызов энкодера на порту E1
brick.encoder("E2") # вызов энкодера на порту E2
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.encoder(E1); // вызов энкодера на порту E1
brick.encoder("E2"); // вызов энкодера на порту E2
```
{% endtab %}
{% endtabs %}

## getStillImage

Получить фотографию с камеры в виде массива байт.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
brick.getStillImage()
```
{% endtab %}

{% tab title="JavaScript" %}
```
brick.getStillImage();
```
{% endtab %}
{% endtabs %}

## gyroscope

Предоставляет доступ к гироскопу (класс «[Gyroscope](class-gyroscope.md)»).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
brick.gyroscope()
```
{% endtab %}

{% tab title="JavaScript" %}
```
brick.gyroscope();
```
{% endtab %}
{% endtabs %}

## keys

Предоставляет доступ к кнопкам на корпусе робота (класс «[Keys](class-keys.md)»).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
brick.keys()
```
{% endtab %}

{% tab title="JavaScript" %}
```
brick.keys();
```
{% endtab %}
{% endtabs %}

## led

Предоставляет доступ к светодиоду на корпусе робота (класс «[Led](class-led.md)»).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
brick.led()
```
{% endtab %}

{% tab title="JavaScript" %}
```
brick.led();
```
{% endtab %}
{% endtabs %}

## lineSensor

Предоставляет доступ к датчику линии по видеокамере (класс «[LineSensor](class-linesensor.md)»).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```
brick.lineSensor("video1")
```
{% endtab %}

{% tab title="JavaScript" %}
```
brick.lineSensor("video1");
```
{% endtab %}
{% endtabs %}

## motor

Предоставляет доступ к мотору (силовому или сервомотору) на указанном порту (класс «[Motor](class-motor.md)»).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.motor(motorName)
brick.motor("motorName")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.motor(motorName);
brick.motor("motorName");
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать порт.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.motor(M1) # вызов мотора на порту M1
brick.motor("M2") # вызов мотора на порту M2
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.motor(M1) // вызов мотора на порту M1
brick.motor("M2") // вызов мотора на порту M2
```
{% endtab %}
{% endtabs %}

## objectSensor

Предоставляет доступ к датчику объекта по видеокамере (класс «[ObjectSensor](class-objectsensor.md)»).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.objectSensor()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.objectSensor();
```
{% endtab %}
{% endtabs %}

## playSound

Проиграть звуковой файл.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.playSound("filename")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.playSound("filename");
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать имя файла с абсолютным путем или путем относительно папки trik на контроллере.

{% hint style="warning" %}
Внимание! Файл должен быть предварительно загружен на контроллер.
{% endhint %}

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.playSound("media/sound.mp3") # проиграть файл sound.mp3 из папки media
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.playSound("media/sound.mp3"); // проиграть файл sound.mp3 из папки media
```
{% endtab %}
{% endtabs %}

## playTone

Проиграть звук с заданной частотой.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.playTone(frequency, time)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.playSound(frequency, time);
```
{% endtab %}
{% endtabs %}

В качестве параметров необходимо указать частоту звука `frequency` и время `time` в мс, в течение которого необходимо проигрывать звук.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.playTone(1000, 1000)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.playTone(1000, 1000);
```
{% endtab %}
{% endtabs %}

## say

Произнести строку (на русском или английском языке).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.say(string)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.say(string);
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать строку на английском или русском языке.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.say("Привет, я ТРИК")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.say("Привет, я ТРИК");
```
{% endtab %}
{% endtabs %}

## sensor

Предоставляет доступ к сенсору на указанном порту (класс «[Sensor](class-sensor.md)»).

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.sensor(portName)
brick.sensor("portName")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.sensor(portName);
brick.sensor("portName");
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать порт.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.sensor(A1) # вызов сенсора на порту A1
brick.sensor("A2") # вызов сенсора на порту A2
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.sensor(A1) // вызов сенсора на порту A1
brick.sensor("A2") // вызов сенсора на порту A2
```
{% endtab %}
{% endtabs %}

## stop

Останавливает все моторы и активные датчики, убирает нарисованное на дисплее.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.stop()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.stop();
```
{% endtab %}
{% endtabs %}

## marker

Предоставляет доступ к рисованию маркером заданного цвета на полу. Доступен только в режиме двумерной модели (класс «[Marker](class-marker.md)»)

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.marker()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.marker();
```
{% endtab %}
{% endtabs %}

