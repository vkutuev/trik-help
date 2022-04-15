# Класс «display»

Предоставляет доступ к дисплею робота.

{% hint style="info" %}
Размер экрана: 240\*320 пикселей.
{% endhint %}

| Метод                                                | Описание                                                                                                                              |
| ---------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| [addLabel](class-display.md#addlabel)                | Вывести на экран указанный текст, начиная с указанной координаты.                                                                     |
| [clear](class-display.md#clear)                      | Очистить окно для рисования.                                                                                                          |
| [drawArc](class-display.md#drawarc)                  | Нарисовать дугу эллипса, вписанного в прямоугольник с левым верхним углом в указанных координатах и имеющий заданную ширину и высоту. |
| [drawEllipse](class-display.md#drawellipse)          | Нарисовать эллипс, вписанный в прямоугольник с левым верхним углом в указанных координатах и имеющий заданную ширину и высоту.        |
| [drawLine](class-display.md#drawline)                | Нарисовать линию с началом и концом в заданных координатах.                                                                           |
| [drawPoint](class-display.md#drawpoint)              | Нарисовать точку в заданных координатах.                                                                                              |
| [drawRect](class-display.md#drawrect)                | Нарисовать прямоугольник с левым верхним углом в указанных координатах и имеющий заданную ширину и высоту.                            |
| [hide](class-display.md#hide)                        | Закрыть и очистить окно для рисования.                                                                                                |
| [redraw](class-display.md#redraw)                    | Перерисовать окно для рисования. Изменения в окне произойдут только после вызова этого метода.                                        |
| [removeLabels](class-display.md#removelabels)        | Удалить с экрана весь текст, добавленный на него вызовами метода «addLabel».                                                          |
| [setBackground](class-display.md#setbackground)      | Установить фон экрана в указанный цвет.                                                                                               |
| [setPainterColor](class-display.md#setpaintercolor)  | Установить цвет кисти, которой рисуются графические примитивы.                                                                        |
| [setPainterWidth](class-display.md#setpainterwidth)	 | Установить толщину кисти, которой рисуются графические примитивы, в пикселях.                                                         |
| [show](class-display.md#show)                        | Вывести на дисплей контроллера изображение, сформированное в одномерном массиве.                                                      |
| [showImage](class-display.md#showimage)              | Вывести на экран изображение, предварительно загруженное на робот.                                                                    |

## addLabel

Вывести на экран указанный текст в указанные координаты. Если в указанных координатах уже был текст, он будет заменён новым.

Изменения на дисплее произойдут только после вызова метода «[redraw](class-display.md#redraw)».

{% tabs %}
{% tab title="Python" %}
```python
brick.display().addLabel("text", x, y)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().addLabel("text", x, y);
```
{% endtab %}
{% endtabs %}

В качестве параметров необходимо указать:

* `text` — выводимый текст,
* `x`, `y` — координаты экрана.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.display().addLabel('Привет, мир!', 1, 1)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().addLabel('Привет, мир!', 1, 1);
```
{% endtab %}
{% endtabs %}

## clear

Очистить окно для рисования.

{% tabs %}
{% tab title="Python" %}
```python
brick.display().clear()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().clear();
```
{% endtab %}
{% endtabs %}

## drawArc

Нарисовать дугу эллипса, вписанного в прямоугольник с левым верхним углом в указанных координатах и имеющий заданную ширину и высоту. Изменения на дисплее произойдут только после вызова метода «[redraw](class-display.md#redraw)».

{% tabs %}
{% tab title="Python" %}
```python
brick.display().drawArc(x, y, l, h, from, to)
```
{% endtab %}

{% tab title="JavaScript" %}
```
brick.display().drawArc(x, y, l, h, from, to);
```
{% endtab %}
{% endtabs %}

В качестве параметров необходимо указать:

* `x`, `y` — координаты левого верхнего угла прямоугольника на экране,
* `l` — ширина прямоугольника,
* `h` — высота прямоугольника,
* `from` __ — начальный угол, ограничивающий дугу,
* `to` __ — конечный угол, ограничивающий дугу.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.display().drawArc(0, 0, 10, 10, 20, 50)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().drawArc(0, 0, 10, 10, 20, 50);
```
{% endtab %}
{% endtabs %}

## drawEllipse

Нарисовать эллипс, вписанный в прямоугольник с левым верхним углом в указанных координатах и имеющий заданную ширину и высоту. Изменения на дисплее произойдут только после вызова метода «[redraw](class-display.md#redraw)».

{% tabs %}
{% tab title="Python" %}
```python
brick.display().drawEllipse(x, y, l, h, filled)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().drawEllipse(x, y, l, h, filled);
```
{% endtab %}
{% endtabs %}

В качестве параметров необходимо указать:

* `x`, `y` — координаты левого верхнего угла прямоугольника,
* `l` — ширина прямоугольника,
* `h` — высота прямоугольника,
*   `filled` — заливать фигуру или нет, по умолчанию `false`

    &#x20;

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.display().drawEllipse(0, 0, 10, 10, True)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().drawEllipse(0, 0, 10, 10, true);
```
{% endtab %}
{% endtabs %}

## drawLine

Нарисовать линию с началом и концом в заданных координатах. Изменения на дисплее произойдут только после вызова метода «[redraw](class-display.md#redraw)».

{% tabs %}
{% tab title="Python" %}
```python
brick.display().drawLine(x0, y0, x1, y1)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().drawLine(x0, y0, x1, y1);
```
{% endtab %}
{% endtabs %}

В качестве параметров необходимо указать:

* `x0`, `y0` — координаты начала линии,
* `x1`, `y1` — координаты конца линии.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.display().drawLine(0, 0, 10, 10)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().drawLine(0, 0, 10, 10);
```
{% endtab %}
{% endtabs %}

## drawPoint

Нарисовать точку в заданных координатах. Изменения на дисплее произойдут только после вызова метода «[redraw](class-display.md#redraw)».

{% tabs %}
{% tab title="Python" %}
```python
brick.display().drawPoint(x, y)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().drawPoint(x, y);
```
{% endtab %}
{% endtabs %}

В качестве параметров необходимо указать координаты точки `x`, `y`.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.display().drawPoint(10, 10)
```
{% endtab %}

{% tab title="JavaScript" %}
```
brick.display().drawPoint(10, 10);
```
{% endtab %}
{% endtabs %}

## drawRect

Нарисовать прямоугольник с левым верхним углом в указанных координатах и имеющий заданную ширину и высоту. Изменения на дисплее произойдут только после вызова метода «[redraw](class-display.md#redraw)».

{% tabs %}
{% tab title="Python" %}
```
brick.display().drawRect(x, y, l, h, filled)
```
{% endtab %}

{% tab title="JavaScript" %}
```
brick.display().drawRect(x, y, l, h, filled);
```
{% endtab %}
{% endtabs %}

В качестве параметров необходимо указать:

* `x`, `y` — координаты левого верхнего угла прямоугольника,
* `l` — ширина прямоугольника,
* `h` — высота прямоугольника,
* `filled` — заливать фигуру или нет, по умолчанию `false`

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.display().drawRect(0, 0, 10, 10, True)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().drawRect(0, 0, 10, 10, true);
```
{% endtab %}
{% endtabs %}

## hide

Закрыть и очистить окно для рисования.

{% tabs %}
{% tab title="Python" %}
```
brick.display().hide()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().hide();
```
{% endtab %}
{% endtabs %}

## redraw

Перерисовать окно для рисования. Изменения на дисплее произойдут только после вызова этого метода.

{% tabs %}
{% tab title="Python" %}
```
brick.display().redraw()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().redraw();
```
{% endtab %}
{% endtabs %}

## removeLabels

Удалить с экрана весь текст, добавленный на него вызовами метода «[addLabel](class-display.md#addlabel)».

{% tabs %}
{% tab title="Python" %}
```
brick.display().removeLabels()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().removeLabels();
```
{% endtab %}
{% endtabs %}

## setBackground

Установить фон экрана в указанный цвет.

Возможные цвета:

* white,
* red, darkRed,
* green, darkGreen,
* blue, darkBlue,
* cyan, darkCyan,
* magenta, darkMagenta,
* yellow, darkYellow,
* gray, darkGray, lightGray,
* black.

{% tabs %}
{% tab title="Python" %}
```python
brick.display().setBackground("color")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().setBackground("color");
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать цвет.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.display().setBackground("red")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().setBackground("red");
```
{% endtab %}
{% endtabs %}

## setPainterColor

Установить цвет кисти, которой рисуются графические примитивы.

Возможные цвета:

* white,
* red, darkRed,
* green, darkGreen,
* blue, darkBlue,
* cyan, darkCyan,
* magenta, darkMagenta,
* yellow, darkYellow,
* gray, darkGray, lightGray,
* black.

{% tabs %}
{% tab title="Python" %}
```python
brick.display().setPainterColor("color")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().setPainterColor("color");
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать цвет.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.display().setPainterColor("red")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().setPainterColor("red");
```
{% endtab %}
{% endtabs %}

## setPainterWidth

Установить толщину кисти, которой рисуются графические примитивы, в пикселях.

{% tabs %}
{% tab title="Python" %}
```python
brick.display().setPainterWidth(d)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().setPainterWidth(d);
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать толщину `d`.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.display().setPainterWidth(5)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().setPainterWidth(5);
```
{% endtab %}
{% endtabs %}

## show

Вывести на дисплей контроллера изображение, преобразованное из однородного массива данных.

{% tabs %}
{% tab title="Python" %}
```python
brick.display().show(array, width, height, format)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().show(array, width, height, format)
```
{% endtab %}
{% endtabs %}

Параметры:

* `array` — одномерный целочисленный массив, имеющий размеры `width`×`height`
* `width` **** и `height` **** — ширина и высота изображения соответственно
* В качестве параметра **format** необходимо передать формат, в котором представлен каждый элемент массива. Сейчас поддержаны форматы: «rgb32», «grayscale8», «rgb888».

#### Пример

Примеры использования `show()` на изображении, снятом с использованием функции [`getPhoto()`](../function-getphoto.md).

{% tabs %}
{% tab title="Python" %}
```python
#rgb32
photo = getPhoto()
brick.display().show(photo, 160, 120, "rgb32")
script.wait(5000)

#rgb888
pic = []
photo = getPhoto()
l = len(photo)
for i in range(l):
    p = photo[i]
    pic.append((p&0xff0000)>>16)
    pic.append((p&0xff00)>>8)
    pic.append((p&0xff))

brick.display().show(pic, 160, 120, "rgb888")
script.wait(5000);                           

#grayscale8                                   
pic = []                                      
photo = getPhoto()
l = len(photo)                        
for i in range(l):                    
    p = photo[i]                  
    pic.append(((p&0xff0000)>>18) + ((p&0xff00)>>10) + ((p&0xff)>>2))               
                                         
                                              
brick.display().show(pic, 160, 120, "grayscale8")
script.wait(5000)

```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
//rgb32
var photo = getPhoto();
brick.display().show(photo, 160, 120, "rgb32");
script.wait(5000);

//rgb888
pic = []
photo = getPhoto();
l = photo.length;
for (i = 0; i < l; i++) {
    var p = photo[i];
    pic.push((p&0xff0000)>>16);
    pic.push((p&0xff00)>>8);
    pic.push((p&0xff));
}
brick.display().show(pic, 160, 120, "rgb888");
script.wait(5000);                            

//grayscale8                                   
pic = []                                      
photo = getPhoto();
l = photo.length;                             
for (i = 0; i < l; i++) {                     
        var p = photo[i];                     
        pic.push(((p&0xff0000)>>18) + ((p&0xff00)>>10) + ((p&0xff)>>2));                
}                                             
                                              
brick.display().show(pic, 160, 120, "grayscale8");
script.wait(5000);
```
{% endtab %}
{% endtabs %}

## showImage

Вывести на экран изображение, предварительно загруженное на робот.

{% tabs %}
{% tab title="Python" %}
```python
brick.display().showImage("imagePath")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().showImage("imagePath");
```
{% endtab %}
{% endtabs %}

В качестве параметра необходимо указать имя файла с изображением (в форматах BMP, GIF, JPG, JPEG, PNG, PBM, PGM, PPM, TIFF, XBM, XPM), путь указывается либо абсолютным, либо относительно папки trik.

#### Пример

{% tabs %}
{% tab title="Python" %}
```python
brick.display().showImage("media/trik_smile_sad.png")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
brick.display().showImage("media/trik_smile_sad.png");
```
{% endtab %}
{% endtabs %}
