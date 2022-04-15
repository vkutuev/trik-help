# Программирование на визуальном языке в TRIK Studio Junior

Программа в TRIK Studio Junior представляется в виде последовательности [блоков](blocks.md), соединённых [связями](connection-between-blocks.md).&#x20;

![](<../../.gitbook/assets/blocks (1).png>)

Каждой программе соответствует [главная диаграмма](./#main-diagramm), которая может содержать [другие диаграммы (подпрограммы)](./#subprogram). Диаграммы упаковываются в проекты, хранящиеся на диске.

![](../../.gitbook/assets/diagram.png)

## Главная диаграмма <a href="#main-diagramm" id="main-diagramm"></a>

Главная диаграмма создаётся при [создании проекта](../start.md#new-project). Про добавление и удаление блоков на [сцену](../../studio/interface/#editor-window-1) читайте в статье:

{% content-ref url="blocks-add-delete.md" %}
[blocks-add-delete.md](blocks-add-delete.md)
{% endcontent-ref %}

## Подпрограммы <a href="#subprogram" id="subprogram"></a>

Диаграммы с подпрограммами создаются автоматически при добавлении блока «Подпрограмма» на сцену. При этом отображение подпрограммы происходит при двойном клике на блок «Подпрограмма» на сцене.

![](../../.gitbook/assets/subprogramm.gif)

Подробнее о подпрограммах читайте в статье:

{% content-ref url="subprograms.md" %}
[subprograms.md](subprograms.md)
{% endcontent-ref %}
