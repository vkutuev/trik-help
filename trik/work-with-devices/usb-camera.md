# Настройка работы USB-камеры с контроллером ТРИК

{% hint style="info" %}
Ниже описана настройка USB-камеры в режиме датчика линии **`lineSensor`**.
{% endhint %}

Для работы с USB-камерой необходимо изменить путь к скрипту в файле `system-config.xml` на контроллере ТРИК.

Это можно сделать с помощью любой из двух утилит:

1. [PuTTY](usb-camera.md#putty).
2. [WinSCP](usb-camera.md#winscp).

## **PuTTy**

1\. [Подключитесь](../wi-fi/network-connection.md) к контроллеру с помощью режима «Wi-Fi точка доступа» или «Wi-Fi клиент».

2\. Откройте [TRIK Studio](https://trikset.com/products/trik-studio).

3\. Запустите утилиту **PuTTY**. Для этого в главном меню откройте `Инструменты → Сторонние программы → PuTTY`.&#x20;

![](<../../.gitbook/assets/putty (1).png>)

4\. Введите [ip-адрес контроллера](../wi-fi/network-connection.md) (указан в параметрах сети контроллера) и нажмите «Open».&#x20;

![](../../.gitbook/assets/putty-connect-1.png)

5\. В открывшемся окне введите `root`. Поле «Пароль» оставьте пустым.

![](https://thumb.tildacdn.com/tild3861-3830-4335-a564-363035666666/-/resize/699x/-/format/webp/putty-login.png)

6\. Введите команду `cd trik` для перехода в соответствующую директорию.

![](https://thumb.tildacdn.com/tild3662-6661-4062-b235-343236393938/-/resize/699x/-/format/webp/putty-4.png)

7\. Для редактирования файла используйте редактор **vi**. Для его запуска введите `vi system-config.xml`.

![](https://thumb.tildacdn.com/tild3034-3532-4566-b363-313431643761/-/resize/699x/-/format/webp/putty-5.png)

8\. С помощью стрелок на клавиатуре перейдите на 62 строку.&#x20;

![](https://thumb.tildacdn.com/tild6561-6166-4263-a566-306666653637/-/resize/991x/-/format/webp/putty-6.png)

```markup
Resolution: 240x320 depth 16
Converting image from 16
Now writing PNG file (compression -1)
```

9\. Нажмите `i` для редактирования, найдите название скрипта `line-sensor-ov7670` и исправьте его на `line-sensor-webcam`.&#x20;

![](https://thumb.tildacdn.com/tild3832-3730-4932-b738-326130613933/-/resize/699x/-/format/webp/putty-7.png)

10\. Для выхода из режима редактирования нажмите «Esc».

11\. Введите команду `:wq` и нажмите «Enter» для сохранения и выхода из редактора **vi**.

## **WinSCP**

1 . В каталоге с установленной TRIK Studio зайдите в папку `winscp` и запустите **WinSCP.exe**.

2\. Заполните данные:

* **File protocol:** SCP.
* **Host name —** [ip-адрес контроллера](../wi-fi/network-connection.md).
* **User name:** root.

Поле «Password» оставьте пустым.&#x20;

![](https://thumb.tildacdn.com/tild6161-3062-4962-a166-356230363430/-/resize/660x/-/format/webp/winscp-login.png)

3\. Нажмите кнопку «Login».

4\. Если у вас появилось окно «Warning», нажмите «Yes».&#x20;

![](https://thumb.tildacdn.com/tild3362-6265-4165-b362-336330666634/-/resize/501x/-/format/webp/winscp-warning.png)

5\. Перейдите в папку `trik`.&#x20;

![](https://thumb.tildacdn.com/tild3763-6232-4062-b462-653464393534/-/format/webp/winscp-3.png)

6\. Найдите и откройте файл `system-config.xml`.

![](https://thumb.tildacdn.com/tild6262-6364-4561-a635-613539643634/-/format/webp/winscp-4.png)

7\. В открывшемся файле на 62 строке найдите название скрипта `line-sensor-ov7670` и исправьте его на `line-sensor-webcam`.&#x20;

![](../../.gitbook/assets/winscp-5.png)

8\. Сохраните изменения, нажав `Ctrl+s` или на иконку «дискеты» в левом верхнем углу, и закройте редактор.

![](https://thumb.tildacdn.com/tild6361-3939-4933-b334-373161656265/-/resize/488x/-/format/webp/winscp-7.png)
