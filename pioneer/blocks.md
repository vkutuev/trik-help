# Блоки квадрокоптера Геоскан Пионер

Блоки, доступные для всех платформ, смотрите в статье

{% content-ref url="../studio/programming-visual/blocks.md" %}
[blocks.md](../studio/programming-visual/blocks.md)
{% endcontent-ref %}



## Блоки квадрокоптера Геоскан Пионер

|                                           Вид                                           |       Название       | Описание                                                                                                                                                                                    |
| :-------------------------------------------------------------------------------------: | :------------------: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|      <img src="../.gitbook/assets/Pioneer_Up_50.png" alt="" data-size="original">       |         Взлёт        | Команда начала полета.                                                                                                                                                                      |
|      <img src="../.gitbook/assets/Pioneer_Dn_50.png" alt="" data-size="original">       |        Посадка       | Команда завершения полета.                                                                                                                                                                  |
|   <img src="../.gitbook/assets/Pioneer_to-point_50.png" alt="" data-size="original">    | Лететь на точку (ЛК) | Указывает точку назначения в локальных координатах. За начало отсчёта (0,0,0) принимается место взлета. Значения координат задаются в метрах.                                               |
| <img src="../.gitbook/assets/getCoordinatesBlock (1).png" alt="" data-size="original">  |  Получить точку (ЛК) | Возвращает текущую позицию в локальной системе координат.                                                                                                                                   |
|      <img src="../.gitbook/assets/Pioneer_Led_50.png" alt="" data-size="original">      |       Светодиод      | Задает цвет светодиода на квадрокоптере.                                                                                                                                                    |
|  <img src="../.gitbook/assets/pioneerMagnetBlock (1).png" alt="" data-size="original">  |         Магнит       | Управляет работой [модуля захвата груза](https://pioneer-doc.readthedocs.io/ru/master/const/module/cargo.html). Чтобы включить магнит, поставьте галочку в чекбоксе значения свойств блока. |
|     <img src="../.gitbook/assets/systemBlock (3).png" alt="" data-size="original">      |        Команда       | Позволяет выполнить команду [на языке Lua](https://pioneer-doc.readthedocs.io/ru/master/programming/lua/lua\_main.html). Для выполнения команды поставьте галочку в чекбоксе.               |
|   <img src="../.gitbook/assets/pioneerYawBlock (1).png" alt="" data-size="original">    |       Рыскание       | Управляет поворотом вокруг вертикальной оси. Для поворота по часовой стрелке, задайте значение угла в градусах со знаком «минус».                                                           |
|   <img src="../.gitbook/assets/readRangeSensor (1).png" alt="" data-size="original">    | Прочитать дальномер  | Считывает информацию с дальномера.                                                                                                                                                          |
