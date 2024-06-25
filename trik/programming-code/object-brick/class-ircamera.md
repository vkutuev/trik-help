# Класс «irCamera»

Предоставляет доступ к инфракрасному датчику MLX90640, подключенному по шине I2C, в режиме камеры и сенсора.

| Метод                                      | Описание                                                                               |
| ------------------------------------------ | ---------------------------------------------------------------------------------------|
| [init](class-ircamera.md#init)             | Инициализирует ИК-камеру и запускает захват кадров.                                    |
| [getImage](class-ircamera.md#getImage)     | Возвращает цветное изображение в виде массива байтов.                                  |
| [readSensor](class-ircamera.md#readSensor) | Возвращает среднее значение температуры в специальной шкале в указанном участке кадра. |
| [stop](class-ircamera.md#stop)             | Останавливает захват кадров.                                                           |

## init

Инициализирует инфракрасную камеру и запускает захват кадров.

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
brick.irCamera().init()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.irCamera().init();
```
{% endtab %}
{% endtabs %}

## getImage

Возвращает цветное изображение ширины `32` и высоты `24` пикселя в виде массива байтов в формате «rgb32».

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
image = brick.irCamera().getImage()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var image = brick.irCamera().getImage();
```
{% endtab %}
{% endtabs %}

#### Пример

Вывод изображения на экран.

{% tabs %}
{% tab title="Python" %}
```python
image = brick.irCamera().getImage()
brik.display().show(image, 32, 24, "rgb32")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var image = brick.irCamera().getImage();
brik.display().show(image, 32, 24, "rgb32");
```
{% endtab %}
{% endtabs %}

## readSensor

Возвращает среднее значение температуры в специальной шкале в указанном участке кадра.

Кадр делится на квадраты сеткой, по умолчанию `3` на `3`, размерность сетки можно задать в `model-config.xml` на роботе.
Квадраты индексируются с `1`. То есть `(1, 1)` — это левый верхний край кадра, `(2, 2)` — его центр.

Возвращаемое значение — среднее значение температуры в указанном квадрате в следующей шкале:
- `-1` — камера не инициализирована
- `0` — соответствует температуре льда из морозильной камеры и ниже
- `1` — соответствует температуре воды из холодильника
- `2` — соответствует температуре в помещении
- `3` — соответствует температуре тела человека
- `4` — соответствует температуре тёплой воды
- `5` — соответствует температуре горячей (близкой к температуре кипения) воды
- `6` — соответствует температуре больше температуры кипения воды

#### Синтаксис

{% tabs %}
{% tab title="Python" %}
```python
temp = brick.irCamera().readSensor(x, y)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var temp = brick.irCamera().readSensor(x, y);
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать индексы квадрата `x` и `y`.

## stop

#### Синтаксис

Останавливает захват кадров до следующего вызова `init()`.

{% tabs %}
{% tab title="Python" %}
```python
brick.irCamera().stop()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.irCamera().stop();
```
{% endtab %}
{% endtabs %}
