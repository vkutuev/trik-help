# Интерфейс TRIK Studio

## Режимы TRIK Studio

Интерфейс TRIK Studio зависит от выбранного режима. TRIK Studio имеет два режима:

1. ****[**Режим редактирования**](./#mode-edit)\
   Предназначен для создания диаграммы управления роботом и исполнения её на роботе в режиме генерации.\

2. ****[**Режим отладки**](./#mode-debug)\
   Предназначен для исполнения и отладки программы на 2D-модели или в режиме интерпретации на реальном роботе.

### Переключение между режимами

Переключение режимов возможно тремя способами. С помощью:

1. Сочетаний клавиш `Ctrl+1` / `Ctrl+2`.
2. [Панели переключения режимов](./#panel-mode-switching).
3. [Строки статуса](./#status-bar).

## Режим редактирования <a href="#mode-edit" id="mode-edit"></a>

![Интерфейс TRIK Studio в режиме редактирования](../../.gitbook/assets/trik-studio-interface.png)

TRIK Studio в режиме редактирования имеет следующие элементы интерфейса:

* [Окно редактора / сцена](./#editor-window)
* [Главное меню](./#menu)
* [Панель «Файл»](./#panel-file)
* [Панель «Правка»](./#panel-edit)
* [Панель «Вид»](./#panel-view)
* [Панель «Интерпретатор»](./#panel-interpreter)
* [Панель «Генераторы»](./#panel-generators)
* [Панель «Прочее»](./#panel-other)
* [Панель переключения режимов](./#panel-mode-switching)
* [Редактор свойств элементов](./#panel-property-editor)
* [Настройки сенсоров](./#panel-configure-devices)
* [Палитра (набор блоков для создания диаграмм)](./#panel-palette)
* [Список переменных](./#panel-variables)
* [Строка статуса](./#status-bar)

### &#x20;<a href="#editor-window" id="editor-window"></a>

### Окно редактора / сцена <a href="#editor-window" id="editor-window"></a>

Сцена отображает диаграмму и позволяет ее редактировать.

![Сцена](../../.gitbook/assets/scene.png)

О создании нового проекта и работе с диаграммами читайте в статьях:

{% content-ref url="../start.md" %}
[start.md](../start.md)
{% endcontent-ref %}

{% content-ref url="../programming-visual/blocks-add-delete.md" %}
[blocks-add-delete.md](../programming-visual/blocks-add-delete.md)
{% endcontent-ref %}

Здесь же осуществляется отображение текущего исполняемого блока при интерпретации диаграмм.

![](<../../.gitbook/assets/04 3 ru chart-interpretation 4.gif>)



### Главное меню <a href="#menu" id="menu"></a>

Главное меню **TRIK Studio** содержит набор базовых операций и настроек среды:

* [Файл](main-menu.md#menu-file)
* [Правка](main-menu.md#menu-edit)
* [Вид](main-menu.md#menu-view)
* [Инструменты](main-menu.md#menu-tools)
* [Настройки](main-menu.md#menu-settings)
* [Справка](main-menu.md#menu-about)

![Главное меню](../../.gitbook/assets/trik-studio-main-menu.png)

Подробнее смотрите в статье:

{% content-ref url="main-menu.md" %}
[main-menu.md](main-menu.md)
{% endcontent-ref %}



### Панель «Файл» <a href="#panel-file" id="panel-file"></a>

Панель «Файл» повторяет основные операции, доступные из меню «[Файл](main-menu.md#menu-file)».

&#x20;<img src="../../.gitbook/assets/newProject.svg" alt="" data-size="line"> Создать новый проект.\
&#x20;<img src="../../.gitbook/assets/open (1).svg" alt="" data-size="line"> Открыть сохраненный проект.\
&#x20;<img src="../../.gitbook/assets/save.svg" alt="" data-size="line"> Сохранить текущий проект.



### Панель «Правка» <a href="#panel-edit" id="panel-edit"></a>

<img src="../../.gitbook/assets/undo.png" alt="" data-size="line"> Отмена операции.\
&#x20;<img src="../../.gitbook/assets/redo.png" alt="" data-size="line">Повтор операции.



### Панель «Вид» <a href="#panel-view" id="panel-view"></a>

Панель «Вид» содержит кнопки, позволяющие масштабировать диаграммы.

<img src="https://thumb.tildacdn.com/tild3030-6165-4761-b762-383737303632/-/resize/65x/-/format/webp/image.png" alt="" data-size="original">Приблизить / отдалить.

Также масштабировать сцену можно с помощью:

1. Зажатия клавиши `Ctrl` и вращения колесика мыши.
2. Сочетания клавиш `Ctrl+=` и `Ctrl+-`.



### Панель «Интерпретатор» <a href="#panel-interpreter" id="panel-interpreter"></a>

![Инструменты панели «Интерпретатор»](https://thumb.tildacdn.com/tild3163-3937-4239-b738-616361666363/-/resize/195x/-/format/webp/image.png)

Панель «Интерпретатор» содержит команды запуска и остановки выполнения программы, кнопки переключения режимов интерпретации между двумерной моделью и реальным роботом, а также кнопку открытия [настроек робота](../settings.md#robots), доступных из меню «Инструменты».&#x20;

При работе с реальным роботом в режиме интерпретации эта панель также содержит кнопку «Подключиться».

<img src="../../.gitbook/assets/robots_run.png" alt="" data-size="line"> Запуск выполнения программы.\
<img src="../../.gitbook/assets/robots_stop.png" alt="" data-size="line"> Остановка выполнения программы.\
<img src="../../.gitbook/assets/2d-model.svg" alt="" data-size="line"> Двумерная модель.\
<img src="../../.gitbook/assets/switch-real-trik.svg" alt="" data-size="line"> Реальный робот.\
<img src="../../.gitbook/assets/robots_settings1.png" alt="" data-size="line"> Настройки робота.



### Панель «Генераторы» <a href="#panel-generators" id="panel-generators"></a>

{% hint style="info" %}
Команды на этой панели изменяются в зависимости от конфигурации программы.
{% endhint %}

Панель «Генераторы» содержит команды генерации кода и загрузки программы на контроллер.

![](https://thumb.tildacdn.com/tild3734-6135-4838-a161-633336393062/-/resize/96x/-/format/webp/image.png)

<img src="../../.gitbook/assets/generateQtsCode.svg" alt="" data-size="line"> Генерировать код.\
<img src="../../.gitbook/assets/uploadProgram.svg" alt="" data-size="line"> Загрузить программу.



### Панель «Прочее» <a href="#panel-other" id="panel-other"></a>

Панель «Прочее» может содержать различную информацию в зависимости от выбранной платформы.

Например, для [конструктора ТРИК](../../trik/about/) на данной панели отображается IP-адрес контроллера, к которому вы подключаетесь.

![](https://thumb.tildacdn.com/tild3736-3338-4131-b737-303964656239/-/resize/129x/-/format/webp/image.png)



### Панель переключения режимов редактирования и отладки <a href="#panel-mode-switching" id="panel-mode-switching"></a>

Панель переключения режимов отображает текущий режим TRIK Studio и позволяет переключаться между режимами редактирования и отладки.

<img src="../../.gitbook/assets/main_tabbar_edit.svg" alt="" data-size="line"> Редактор.\
<img src="../../.gitbook/assets/main_tabbar_debug.svg" alt="" data-size="line"> Отладка.



### Панель «Редактор свойств» <a href="#panel-property-editor" id="panel-property-editor"></a>

Редактор свойств используется для отображения и редактирования значений свойств выделенных объектов (блоков, связей).&#x20;

![Панель «Редактор свойств»](../../.gitbook/assets/panel-property-editor.png)

О работе с редактором смотрите статью:

{% content-ref url="../programming-visual/editing-element-properties.md" %}
[editing-element-properties.md](../programming-visual/editing-element-properties.md)
{% endcontent-ref %}



### Панель «Настройки сенсоров» <a href="#panel-configure-devices" id="panel-configure-devices"></a>

Настройки сенсоров позволяют указать, какие сенсоры использованы на каком порту. То же можно сделать из диалога настроек робота.

{% hint style="info" %}
Набор сенсоров зависит от выбранной платформы в настройках на вкладке «[Роботы](../settings.md#robots)».
{% endhint %}

![Настройки сенсоров для контроллера ТРИК](https://thumb.tildacdn.com/tild6130-6533-4832-a631-656535393432/-/resize/354x/-/format/webp/\_-8.png)

###

### Панель «Палитра» <a href="#panel-palette" id="panel-palette"></a>

Палитра элементов содержит набор доступных блоков и связей между ними, которые можно добавить на диаграмму.

{% hint style="info" %}
1. Состав палитры может меняться в зависимости от выбранной в [настройках](../settings.md#robots) платформы.
2. Серым выделены блоки, недоступные в выбранной модели выполнения (2D-модели или на реальном роботе).
{% endhint %}

![Панель «Палитра»](https://thumb.tildacdn.com/tild6465-6266-4364-b032-663531326133/-/resize/345x/-/format/webp/\_-9.png)

О добавлении и удалении блоков на сцену в TRIK Studio читайте в статье:

{% content-ref url="../programming-visual/blocks-add-delete.md" %}
[blocks-add-delete.md](../programming-visual/blocks-add-delete.md)
{% endcontent-ref %}



### Панель «Переменные» <a href="#panel-variables" id="panel-variables"></a>

Список переменных, используемых при выполнении диаграммы с их текущими значениями, включая [сенсорные переменные](../programming-visual/expression-syntax/sensory-variables.md). При исполнении в режиме интерпретации на двумерной модели или реальном роботе берутся с робота в реальном времени. В режиме генерации не используются.

![Панель «Переменные»](https://thumb.tildacdn.com/tild3136-3865-4436-b937-326431666135/-/resize/345x/-/format/webp/\_-10.png)

###

### Строка статуса <a href="#status-bar" id="status-bar"></a>

Строка статуса отображает текущий режим TRIK Studio ([редактирования](./#mode-edit) или [отладки](./#mode-debug)) и позволяет переключаться между режимами. Для переключения достаточно кликнуть на строку статуса.

![Строка статуса](../../.gitbook/assets/pnl-status-bar.png)



## Режим отладки <a href="#mode-debug" id="mode-debug"></a>

Элементы интерфейса TRIK Studio в режиме отладки повторяют элементы в [режиме редактирования](./#mode-edit), кроме окна редактора, панелей редактора свойств и палитры. Вместо этих элементов отображаются:

* [Окно «Двумерная модель»](./#window-2-d-1)
* [Окно «Ошибки»](./#window-error)
* [Панель «Настройки робота»](./#panel-settings-robot)
* [Панель «Графики»](./#panel-graphics)

![Режим отладки](../../.gitbook/assets/trik-studio-mode-debug.png)

### &#x20;<a href="#window-2-d" id="window-2-d"></a>

### Окно «Двумерная модель» <a href="#window-2-d" id="window-2-d"></a>

Окно «Двумерная модель» открывается, если в качестве режима исполнения программы выбрана 2D-модель.

![Окно 2D-модели](../../.gitbook/assets/window-2d-model.png)

Окно позволяет задать окружение, в котором будет работать робот, задать датчики робота и наблюдать, как будет работать написанная в режиме редактирования программа.

Подробнее о 2D-модели читайте в статье:

{% content-ref url="../2d-model/" %}
[2d-model](../2d-model/)
{% endcontent-ref %}

{% hint style="info" %}
В режиме интерпретации и генерации программы на реальном роботе это окно не показывается, вместо него отображается исполняемая диаграмма.
{% endhint %}

###

### Панель «Настройки робота» <a href="#panel-settings-robot" id="panel-settings-robot"></a>

На панели настроек робота отображается вид контроллера и параметры робота, которые зависят от выбранной [платформы](../about/#platforms).

![Панель «Настройки робота»](../../.gitbook/assets/panel-settings-robot.png)

#### Открытие панели «Настройки робота»

![](<../../.gitbook/assets/04 D ru panel-controller-open 2.gif>)



### Окно «Ошибки» <a href="#window-error" id="window-error"></a>

В случае синтаксических и семантических ошибок в TRIK Studio появляется окно с соответствующими сообщениями.

Для просмотра блока, в котором допущена ошибка, необходимо кликнуть на сообщение.

![](<../../.gitbook/assets/04 F ru panel-error 2.gif>)

###

### Панель «Графики» <a href="#panel-graphics" id="panel-graphics"></a>

Окно «Графики» отображает в реальном времени значения, присылаемые датчиками.&#x20;

![](<../../.gitbook/assets/04 G ru panel-graphics.png>)

Подробнее читайте в статье:

{% content-ref url="graphics.md" %}
[graphics.md](graphics.md)
{% endcontent-ref %}
