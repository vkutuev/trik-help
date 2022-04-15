# Функция getPhoto

## Описание функции

Функция возвращает одномерный массив байт, в который записаны пиксели изображения в формате **`rgb32`**, снятого с камеры (размер изображения — 160x120). Данная функция может быть использована для решения задач распознавания маркеров.

## Вызов функции

{% tabs %}
{% tab title="Python" %}
```python
pic = getPhoto()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var pic = getPhoto();
```
{% endtab %}
{% endtabs %}

## Пример работы

Рассмотрим пример преобразования кадра, снятого на камеру, в цветовые форматы «оттенок серого» и «черно-белый».

Сделайте снимок и выведите результат на экран c помощью функции [**show**](object-brick/class-display.md#show).

{% tabs %}
{% tab title="Python" %}
```python
# взять кадр в формате rgb32
pic = getPhoto()
brick.display().show(pic, total_height, total_width, "rgb32")
script.wait(2000)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
// взять кадр в формате rgb32
var pic = getPhoto();
brick.display().show(pic, total_height, total_width, "rgb32");
script.wait(2000);
```
{% endtab %}
{% endtabs %}

Результат:

![](https://thumb.tildacdn.com/tild6535-6131-4638-b834-323461306536/-/resize/240x/-/format/webp/getphoto1.png)

## Реализация функции перевода изображения в оттенок серого

{% tabs %}
{% tab title="Python" %}
```python
def grayScale(sPic):
	bufPic = []
	for i in range(total_height):
		for j in range(total_width):
			x = i * total_width + j
			p = sPic[x]
			r = (p & 0xff0000) >> 16	# взять значение компоненты красного
			g = (p & 0xff00) >> 8 # взять значение компоненты зеленого
			b = (p & 0xff) # взять значение компоненты синего
			p = r * 0.299 + g * 0.587 + b * 0.114; # компонента Y из YUV
			bufPic.append(p)
	return bufPic
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
function grayScale(sPic){
	bufPic = [];
	for(var i = 0; i < total_height; i++)
		for(var j = 0; j < total_width; j++){
			var x = i * total_width + j;
			var p = sPic[x];
			var r = (p & 0xff0000) >> 16;	// взять значение компоненты красного
			var g = (p & 0xff00) >> 8;	// взять значение компоненты зеленого
			var b = (p & 0xff);		// взять значение компоненты синего
			p = r * 0.299 + g * 0.587 + b * 0.114; // компонента Y из YUV
			bufPic[x] = p; 
		}
	return bufPic;
}
```
{% endtab %}
{% endtabs %}

Перевод изображения в черно-белый формат и вывод на дисплей:

{% tabs %}
{% tab title="Python" %}
```python
pic = grayScale(pic)

brick.display().show(pic, total_height, total_width, "grayscale8")
script.wait(2000)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var pic = grayScale(pic);

brick.display().show(pic, total_height, total_width, "grayscale8");
script.wait(2000);
```
{% endtab %}
{% endtabs %}

Результат:

![](https://thumb.tildacdn.com/tild3136-3162-4264-b135-313732663734/-/resize/240x/-/format/webp/getphoto2.png)

## Реализация функции бинаризации изображения

{% tabs %}
{% tab title="Python" %}
```python
# Бинаризация -- перевод изображения в ЧБ
def binarization(treshold, sPic):
	bufPic = []
	for i in range(len(sPic)):
		bufPic.append(255 if sPic[i] > treshold else 0)
	return bufPic
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
// Бинаризация -- перевод изображения в ЧБ
function binarization(treshold, sPic){
	bufPic = []
	for(var i = 0; i < sPic.length; i++){
		bufPic[i] = sPic[i] > treshold ? 255 : 0;
	}
	return bufPic;
}
```
{% endtab %}
{% endtabs %}

Перевод изображения в черно-белого и вывод на дисплей:

{% tabs %}
{% tab title="Python" %}
```python
pic = binarization(80, pic)
brick.display().show(pic, total_height, total_width, "grayscale8")
script.wait(2000)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var pic = binarization(80, pic);
brick.display().show(pic, total_height, total_width, "grayscale8");
script.wait(2000);
```
{% endtab %}
{% endtabs %}

Результат:&#x20;

![](https://thumb.tildacdn.com/tild3430-3165-4933-b962-626438366662/-/resize/240x/-/format/webp/getphoto3.png)

{% hint style="info" %}
[Пример программы с использованием функции getPhoto](https://dl.trikset.com/trikset-help/getPhoto.js).
{% endhint %}

{% hint style="info" %}
Дополнительный материал: презентация Университета Иннополис «[Распознавание меток ARTag](https://drive.google.com/file/d/15jbnB8Yv2HZq51Hwwi1jAu7dPtxyN8TS/view)».
{% endhint %}
