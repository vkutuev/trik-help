# Веб-интерфейс контроллера ТРИК

Веб-интерфейс контроллера ТРИК позволяет:

* [Изменить настройки Wi-Fi на контроллере.](web-interface.md#set)
* [Настроить взаимодействие нескольких контроллеров.](web-interface.md#set)
* [Изменить конфигурацию датчиков, моторов и энкодеров.](web-interface.md#porty)
* [Изменить конфигурацию микроэлектромеханических систем (гироскоп и акселерометр).](web-interface.md#mems)
* [Запустить видеотрансляцию с камеры контроллера.](web-interface.md#videotranslyaciya)
* [Скачать лог-файлы.](web-interface.md#bortovoi-zhurnal)
* [Посмотреть программы, загруженные на контроллер.](web-interface.md#programmy)
* [Сделать скриншоты экрана контроллера и скачать их.](web-interface.md#izobrazheniya)
* [Сделать снимки с камеры, подключенной к контроллеру, и скачать их.](web-interface.md#izobrazheniya)

## Запуск веб-интерфейса

‌Для запуска веб-интерфейса:

1. Подключите контроллер ТРИК к компьютеру любым из [возможных способов](wi-fi/network-connection.md).
2. Введите в адресной строке браузера IP-адрес контроллера.

![Пример ввода IP-адреса](https://lh4.googleusercontent.com/8Dqrd13QCRPWKrIQoD8IPvgMdIYyI2vNabe8JDQxW1o5RGSkI6vM-CurBL5GtXbDzqdFODH-0uKFnYNJhIs4S8waXds6cDGJI5a0Z\_\_AYBy7knvWh8zh2V\_5-ouwGcgk-b3vQaoo)

IP-адрес контроллера отображается на экране после подключения к сети.

![](https://lh3.googleusercontent.com/iRtyRma-5whbUFs6X0QXeJxGl-57aqG3GJjxmQQ4KVKmV-p95nyqs6wUNGv1JqMVR8gV7BUr6FG9hthw16klwaNGyB1-LQbApCisv3dTwh6DTyq87YTnoafEyFJYzV8oH8vrHhgH)

## Меню веб-интерфейса

Меню веб-интерфейса содержит следующие пункты:

1. [Сеть.](web-interface.md#set)
2. [Порты.](web-interface.md#porty)
3. [МЭМС (микроэлектромеханические системы).](web-interface.md#mems)
4. [Видеотрансляция.](web-interface.md#videotranslyaciya)
5. [Бортовой журнал.](web-interface.md#bortovoi-zhurnal)
6. [Программы.](web-interface.md#programmy)
7. [Изображения.](web-interface.md#izobrazheniya)

## Сеть

На вкладке «Сеть» можно:

* ‌Задать параметры Wi-Fi-сети для контроллера в режиме точки доступа [Wi-Fi-клиента](wi-fi/network-connection.md#client).
* Изменить имя точки доступа Wi-Fi для контроллера в режиме [точки доступа Wi-Fi](wi-fi/network-connection.md#accesspoint).
* Задать бортномер контроллера и IP-адрес ведущего контроллера для [взаимодействия контроллеров](wi-fi/interaction/).
* Включить или отключить PPP-демон (PPP-демон нужен для эмуляции сетевого подключения через последовательный порт).

![Вкладка «Сеть»](https://lh6.googleusercontent.com/pqcyQadVMo8y9EM1VVEHXJcLAwlGPeykZC4nmAYKohSX4mtFnmjGhJcrSxx7Rnv1tCmZ612-r1CMSKpg0iDBA9fxt7sXDPg0XxuplnDSDH3yu6fV5K2yHUgC1mNhgy3AnQZB8DTv)

## Порты

На вкладке «Порты» можно:

* Выбрать тип подключаемых [силовых моторов](web-interface.md#silovye-motory) для каждого порта.
* Выбрать тип подключаемых [сервомоторов](web-interface.md#servomotory) для каждого порта.
* Выбрать тип подключаемых [аналоговых датчиков](web-interface.md#analogovye-sensory) для каждого порта.
* Выбрать тип [энкодеров](web-interface.md#enkodery), использующихся в моторах, для каждого порта, а также положительное направление отсчета положения вала мотора для каждого порта.
* Выбрать тип подключаемых [цифровых датчиков](web-interface.md#datchiki-distancii) для каждого порта.
* Сконфигурировать порты для подключения [видеокамер](web-interface.md#video1-video2).

![](<../.gitbook/assets/WI-10-Port (1).png>)

После изменения настроек необходимо нажать на кнопку «Сохранить» внизу экрана и подтвердить действие.

![](https://lh3.googleusercontent.com/cPkUdk7HyBuL1DtzCaHxrZyEzBtWtqI5q0CSzuUj\_5hX4u4o9z4e8vvSm4wJRrpkywiJeA417dkNNnJZi\_lZ0fqsODoEbONpE61SFZ8TdMjUT65vY8fh3FR7NVQjUx9co4k9y6RS)

### Силовые моторы

В разделе «Силовые моторы» вы можете выбрать тип подключаемых силовых моторов для каждого порта.

### Сервомоторы

В разделе «Сервомоторы» вы можете выбрать тип подключаемых сервомоторов для каждого порта.

### Аналоговые сенсоры

В разделе «Аналоговые сенсоры» вы можете выбрать тип подключаемых аналоговых сенсоров для каждого порта.

### Энкодеры

В разделе «Энкодеры» вы можете выбрать тип энкодеров, использующихся в моторах, для каждого порта, а также положительное направление отсчета положения вала мотора для каждого порта.

### Датчики дистанции

В разделе «Датчики дистанции» вы можете выбрать тип подключаемых цифровых датчиков для каждого порта.

### Video1 / Video2

Видеопорты и подключенные к ним видеокамеры могут работать в следующих режимах:

* colorSensor3x3 — режим датчика цвета.
* lineSensor — режим сенсора линии с детектированием цвета.
* photo — камера используется для получения снимков и видеопотока.
* edgeLineSensor — режим сенсора линии с детектированием границ (работает на инверсных линиях).

![](../.gitbook/assets/WI-22-Video.png)

## МЭМС

Вкладка МЭМС (микроэлектромеханические системы) позволяет:

* Включить или отключить гироскоп или акселерометр.
* Выбрать частоту обновления и диапазон работы акселерометра и гироскопа в «Расширенных настройках».

![](https://lh4.googleusercontent.com/AYpIMeubH2ZyBByHeB37oYtAOnOO\_voBfOcsb44CAoyij6GFKtW54Mv-rrPS6hfoZGY1hmumJZvflID-E\_deehGRK-EIg81rRqLiDmrFa4UVIg4TESOimkH48EIp4x1x2QYKjy8Q)

Для изменения конфигурации необходимо нажать кнопку «Сохранить» и подтвердить действие.

![](https://lh5.googleusercontent.com/6qgUIBFewE5C1re6c12IYzh7yhUaiCrAaoeiFDbJN1g43QavyastAIuTkKY54vDl9burYWfq1HE4CGszUwng4mDyiTPGkhOpXQRVMuBsCNVodBOeLdq3Eu55\_jGcnPBQ-ol4gM2f)

## Видеотрансляция

Вкладка «Видеотрансляция» позволяет смотреть видео с установленной на контроллере камеры.

Для её запуска необходимо в [программу управления роботом с пульта](../gamepad/remote-control.md) добавить блок «[Запустить видеотрансляцию](programming-visual/blocks.md#camera-on)».

## Бортовой журнал

На вкладке «Бортовой журнал» отображаются логи контроллера, которые можно скачать [для последующей отправки их в службу поддержки](../feedback/logging.md#trik).

![](https://lh3.googleusercontent.com/gSw8G3IcE5WolWHUJSpZlaBou1jVur3MY12FkxpU6\_Zbl\_j49p3-XzsLa2TqG40IWm\_JunJeM7sYQ6UhxRY1s9ZlJWju84ZjKUyZXDaf0NFjuzxKGqQedqwm2ZwNJDn7EQ0iALz-)

## Программы

На вкладке «Программы» отображаются загруженные на контроллер программы.

![](<../.gitbook/assets/WI-82 Progs.png>)

Удалить все программы можно через интерфейс контроллера.

![](<../.gitbook/assets/WI-84 Progs.png>)

![](<../.gitbook/assets/WI-86 Progs.png>)

## Изображения

Вкладка «Изображения» содержит изображения, сделанные с помощью подключенной камеры, а также скриншоты экрана контроллера.

На вкладке вы можете:

* [Сделать снимок экрана контроллера](about/screenshot.md).
* Просмотреть и скачать полученные с контроллера изображения как по отдельности, так и все вместе.
* Удалить все имеющиеся изображения (выборочного удаления не предусмотрено).

![](<../.gitbook/assets/WI-95 Images.png>)

## LOG

Иконка <img src="../.gitbook/assets/logs2 (1).png" alt="" data-size="line"> позволяет скачать лог-файлы. Подробнее читайте в статье «Действия при неправильной работе TRIK Studio или контроллера ТРИК» в разделе «[Сбор логов на контроллере ТРИК](../feedback/logging.md#trik)».
