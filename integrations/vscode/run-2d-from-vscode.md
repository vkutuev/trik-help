# Запуск 2D-модели в TRIK Studio из VSCode

В данной статье рассматривается настройка и использование внешней среды программирования **VSCode** для вызова программ в [2D-модели](../../studio/2d-model/) TRIK Studio.&#x20;

Это позволит опытным пользователям TRIK Studio использовать все возможности профессиональных текстовых редакторов и их плагинов: статические анализаторы, автоформаттеры, цветовые темы.

Также рассказывается как автоматически запускать программу на нескольких полях, что может быть полезно участникам соревнований с автоматизированными системами проверки (например, [Олимпиады НТИ ИРС](https://trikset.com/education/nti)).

## **Подготовка** <a href="#configure" id="configure"></a>

Предполагается, что пользователь пишет программу во внешнем редакторе и хотел бы запустить данную программу на одном или нескольких полях. Поля могут быть представлены как в формате `.xml` (подробнее в статье [«Гибкая настройка 2D-модели»](../../studio/2d-model/settings.md)), так и в формате `.qrs`.

1. Скачайте файл [run\_2d\_model.cmd](https://gist.github.com/anastasiia-kornilova/2b955e62c3cef7a509fc043a189ea3ff) для Windows или [run\_2d\_model.sh](https://gist.github.com/anastasiia-kornilova/f13a708562debabeeb126381f3d535e5) для Linux и поместите его в папку, в которой установлена TRIK Studio.
2. Поместите поля, на которых необходимо тестировать программу, в отдельную папку. Если поля представлены в формате `xml`, создайте в данной папке пустой проект `default.qrs`.

{% hint style="warning" %}
Инструкция протестирована на январском релизе 2020 года (version 1.42).\
Скачать VSCode можно на [официальном сайте](https://code.visualstudio.com/Download).
{% endhint %}

## Настройка **VSCode**

1\. Создайте папку, в которой будет находиться файл с исходным кодом.

2\.  Откройте эту папку в **VSCode** c помощью `File → Open Folder`.

3\.  Вызовите `Terminal → Configure Tasks`.

![](../../.gitbook/assets/VSCode\_1.png)

4\. Если ранее задач не было, то выберите в выпадающем меню `Create tasks.json file from template → Others`. Откроется файл `tasks.json`. \
Если tasks были созданы ранее, он откроется сразу после пункта 3.

![](../../.gitbook/assets/VSCode\_2.jpg)

5\. Удалите всё из этого файла и вставьте данный код, где `<path to field dir>` — полный путь к папке с полями:

```javascript
{
"version": "2.0.0",
	"tasks": [ {
		"label": "Run TRIK 2D model",
		"type": "shell",
		"command": "/home/admin/TRIKStudio/run_2d_model.sh" <path to fields dir> script.js",
		"windows": {
			"command": "D:\\TRIKStudio\\run_2d_model.cmd  <path to fields dir> script.js"
		},
		"group": "test",
		"presentation": {
			"reveal": "always",
			"panel": "new"
		}
	}]
}
```

6\. В зависимости от вашей операционной системы отредактируйте файл `tasks.json`:

* Для Linux необходимо в строке, соответствующей полю `"command"`, указать путь к отредактированному `run_2d_model.sh` и третьим аргументом указать файл вашего исходного кода. Данный файл должен находиться в папке, которую мы открыли с помощью **VSCode**. Например: `"command": "/home/admin/TRIKStudio/run_2d_model.sh /home/admin/fields/ script.js"`
* Для Windows необходимо в строке соответствующей полю `"windows": { "command"` указать путь к отредактированному `run_2d_model.cmd` и третьим аргументом указать файл вашего исходного кода. Данный файл должен находиться в папке, которую мы открыли с помощью **VSCode**. Например:\
  `"command": "D:\TRIKStudio\run_2d_model.cmd D:\Users\Admin\fields script.js"`

![](../../.gitbook/assets/VSCode\_3.png)

7\. Сохраните файл `tasks.json`.

8\. Теперь при нажатии `Terminal → Run Task` в выпадающем меню выберите`Run TRIK 2D model,` чтобы запустить ваш код, или соответствующую комбинацию клавиш (**Ctrl+Shift+B**).&#x20;

![](../../.gitbook/assets/VSCode\_4.jpg)

{% hint style="success" %}
За предложение добавить данную функциональность команда проекта ТРИК благодарит участника Олимпиады НТИ ИРС 2018—2020 гг. **Александра Журавлева**.
{% endhint %}
