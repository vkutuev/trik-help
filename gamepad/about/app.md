# Приложение TRIK Gamepad

Скачать бесплатно приложение для Android или iOS вы можете [в магазинах](https://trikset.com/products/trik-gamepad).

## Интерфейс <a href="#interface" id="interface"></a>

Интерфейс приложения включает:

* **Pad1, Pad2** — программируемые области для нажатия.
* **Индикаторы последнего нажатия** на экран.
* **Программируемые кнопки (5 шт)** — кнопки для программирования дополнительных функций.
* **Настройки** — настройки подключения к роботу.

![](https://thumb.tildacdn.com/tild6638-3230-4934-b532-386466386438/-/format/webp/trik-gamepad-app.png)

В приложении имеется возможность трансляции видео с камеры, подключенной к роботу.

Для её запуска необходимо в [программу управления роботом с пульта](../remote-control.md) добавить блок «[Запустить видеотрансляцию](../../trik/programming-visual/blocks.md#camera-on)».

## Принцип работы

За работоспособность геймпада отвечает несколько сенсорных переменных:

* gamepadPad1Pressed, gamepadPad2Pressed.
* gamepadPad1, gamepadPad2.
* gamepadButton1, …, gamepadButton5.
* gamepadConnected.

{% hint style="info" %}
Подробнее с сенсорными переменными TRIK Gamepad вы можете ознакомиться в статье «[Сенсорные переменные для контроллера ТРИК](../../trik/programming-visual/sensory-variables.md)».
{% endhint %}
