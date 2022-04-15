# Программирование LEGO EV3 для Virtual Robotics Toolkit в TRIK Studio

TRIK Studio можно использовать для написания программ для симулятора контроллера LEGO EV3 [Virtual Robotics Toolkit](https://www.virtualroboticstoolkit.com) (VRT).

Для написания и загрузки программы в VRT необходимо:

1. На визуальном языке [написать программу ](../studio/programming-visual/)для [LEGO EV3](run-upload-programs.md).
2. В любом из режимов робота LEGO EV3 («Автономный режим (USB)», «Автономный режим (Bluetooth)», «Интерпретатор (USB)», «Интерпретатор (Bluetooth)») нажать кнопку «Загрузить программу». В результате этого создастся исполняемый файл `.rbf` в папке `%APPDATA%\trik-studio\ev3-rbf`.
3. Запустить VRT.
4. Запустить [EV3 Explorer](https://sites.google.com/site/ev3basic/ev3-explorer) и подключиться к виртуальному роботу в VRT по Wi-Fi (IP-адрес: `127.0.0.1`).
5. Отправить исполняемый файл `.rbf` на виртуального робота.
6. Запустить загруженный в VRT файл.

## Пример программы в TRIK Studio для VRT

Алгоритм:

![](../.gitbook/assets/program\_for\_vrt.png)

Исполнение в VRT:

![](../.gitbook/assets/program\_for\_vrt.gif)

{% hint style="info" %}
Благодарим Алексея Михайловича Клячина за помощь при написании статьи.
{% endhint %}
