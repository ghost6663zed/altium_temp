Программа для управления режимами работы платы питания MAR и вывода текста на LCD экран.
Подключение через UART, скорость 9600.

Для компиляции в среде 	Arduino IDE необходимо установить библиотеки:
-LiquidCrystal
-SerialCommands

Инструменты -> Управлять библиотеками, в появившемся окошке набрать название библиотеки, потом нажать кнопку Install

Окончание команды - <CR>
Описание команд:

Управление питанием модемной платы:
PWR <VALUE>

<VALUE> - 0 - отключить питание модемной платы, 1 - включить питание модемной платы.
По умолчанию на модемной плате питание выключено


При инициализации микроконтроллера происходит поиск LCD экрана на шине I2C. Если экран найден, происходит его инициализация - вывод надписи "Loading ..." и мигающего курсора.

Вывод текста на LCD экран
ECHO <ROWNUM> <TEXT1> [<TEXT2> ... <TEXTn>]

<ROWNUM> - номер строки LCD экрана, на которую следует вывести текст. Возможные значения - 1 и 2.

[<TEXT2> ... <TEXTn>] - текст, который нужно вывести. Разделители между словами - пробел, максимальное количество символов (включая разделители) - 16. 
Если количество символов - менее 16, производится очистка экрана до конца указанной строки.

Очистка LCD экрана
CLEAR <ROWNUM>
<ROWNUM> 0 - Производится очистка всего экрана.
<ROWNUM> 1 - Производится очистка строки 1.
<ROWNUM> 2 - Производится очистка строки 2.

Управление линиями данных SIM модемной платы:
SIM <VALUE>

<VALUE> - 0 - отключить линии данных SIM модемной платы, 1 - включить линии данных SIM модемной платы.
По умолчанию на модемной плате линии данных SIM выключены 

