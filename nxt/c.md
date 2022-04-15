# Программирование LEGO NXT на C

Текстовое программирование для LEGO NXT осуществляется на языке C с использованием макросов и функций из библиотеки ECRobot.

Общая структура программы:

* Сначала идёт подключение заголовочных файлов, используемых в программе (стандартные заголовочные файлы C и заголовочные файлы ECRobot).
* Затем идёт объявление констант и переменных, используемых в программе.
* За ними описываются функции `ecrobot_device_initialize` и `ecrobot_device_terminate`. Первая вызывается при запуске программы, вторая — при прекращении её работы. В них обычно выполняется инициализация и деинициализация датчиков, энкодеров и других устройств робота. По умолчанию в `ecrobot_device_initialize` инициализируется генератор случайных чисел.
* За ними идёт описание функции `user_1ms_isr_type2`, которая вызывается каждую миллисекунду.
* Затем идёт описание задачи, которая запускается на исполнение при старте программы: `TASK (OSEK_Task_Number_0)`. Здесь, собственно, и выполняется большая часть программирования.

```c
#include <string.h>
#include "kernel.h"
#include "kernel_id.h"
#include "ecrobot_interface.h"
#include "trik_studio_utils.h"
#include <time.h>
#include <stdlib.h>
#include <stdio.h>
#include <stdarg.h>
#include <math.h>

U32 __interpretation_started_timestamp__ = 0;
static const float pi = 3.14159265;



void ecrobot_device_initialize(void)
{
	srand(systick_get_ms());

}

void ecrobot_device_terminate(void)
{

}

/* nxtOSEK hook to be invoked from an ISR in category 2 */
void user_1ms_isr_type2(void)
{

}

/* Main task */
TASK(TASK_MAIN)
{
	__interpretation_started_timestamp__ = systick_get_ms();

	TerminateTask();
}
```

{% hint style="info" %}
[Полное описание](http://lejos-osek.sourceforge.net/api.htm) функций на английском, доступных при программировании.

В качестве примеров можно использовать код, генерируемый по диаграммам самой средой TRIK Studio.
{% endhint %}
