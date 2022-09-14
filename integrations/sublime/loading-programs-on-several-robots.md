# Загрузка программ на нескольких роботов ТРИК из Sublime Text

В данной статье рассматривается возможность одновременной загрузки программ на группу роботов с использованием внешнего текстового редактора **Sublime Text**. Статья является продолжением материала

{% content-ref url="run-2d-from-sublime.md" %}
[run-2d-from-sublime.md](run-2d-from-sublime.md)
{% endcontent-ref %}

## Настройка

Скачайте файл [send\_files.cmd](https://gist.github.com/anastasiia-kornilova/e1344f658a91449cf16217ec03147a18) для Windows и поместите его в папку, в которую установлена TRIK Studio.

{% hint style="warning" %}
Инструкция протестирована на Sublime Text 3 (Build 3211).\
Скачать Sublime Text можно на [официальном сайте](https://www.sublimetext.com/).
{% endhint %}

Перед первым запуском программы необходимо зайти на контроллер ТРИК через WinSCP. Инструкция о том, как это сделать, доступна по [ссылке](../../studio/utilities/winscp.md). После этого WinSCP запомнит, что было разрешено устанавливать соединение с этим роботом и не будет требовать подтверждений. Это действие необходимо повторять при подключении каждого нового контроллера.

1\. Откройте Sublime Text.

2\. Выберите `Tools → Build System → New Build System`

![](<../../.gitbook/assets/Sublime\_1 (1).png>)

3\. Откроется окно с текстовым файлом. В нем необходимо всё стереть и вставить вместо этого следующий код:

```javascript
{
"cmd": ["D:\\TRIKStudio\\send_filesl.cmd", “<path to scripts dir>”, "<file with ip addresses>"],
"selector": "source.js"
}
```

Здесь:

* `<path to scripts dir>` — полный путь к папке с программами, которые необходимо загрузить на роботов, &#x20;
* `<file with ip addresses>` — название файла `.txt`, в котором содержатся ip-адреса роботов для загрузки файлов. Каждый ip-адрес на новой строке. Файл с ip-адресами роботов должен находиться в той же папке, что и отправляемые программы.

4\. Укажите свой путь к файлу `send_files.cmd` вместо указанного в коде. Например:

```javascript
"cmd": ["C:\\TRIKStudio\\send_files.cmd", "C:\\Users\\Admin\\myfiles", "ip_addr.txt"]
```

![](<../../.gitbook/assets/Sublime\_2 (1).png>)

5\. Сохраните этот текстовый файл в предлагаемой директории `<папка с системными файлами>\Sublime Text 3\Packages\User` под именем `TRIK_SEND.sublime-build`.

6\. Выберите `Tools → Build System` и в открывшемся списке выберите `TRIK_send`.

![](../../.gitbook/assets/Sublime\_3.png)

7\. Для начала отправки программ на роботов достаточно нажать `Tools → Build` или соответствующую комбинацию клавиш `Ctrl+B`. Для того чтобы вернуться к [запуску 2D-модели](run-2d-from-sublime.md), необходимо выбрать `Tools → Build System` и в открывшемся списке выбрать `TRIK`.

![](../../.gitbook/assets/Sublime\_4.png)
