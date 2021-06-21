# Business Days Calculator
Программный код на базе WebSoft HCM (WebTutor) для определения выходных, праздничных, а также сокращенных дней.

## Как использовать
Для иниициализации библиотеки необходимо подключить её с помощью функции `RegisterCodeLibrary()`, которую рекомендуется обернуть в блок `try {} catch() {}`, так как, если библиотека уже была инициализирована ранее - произойдёт ошибка.

### Пример подключения
```javascript
try { RegisterCodeLibrary("x-local://wtv/external/bdc/bdc.bs"); } catch(err) {}
```

### Пример использования
```javascript
bdc.isDayOff(Date("01.01.2021"));           // -> true
bdc.isWorkingDay(Date("12.01.2021"));       // -> true
bdc.isNonWorkingDay(Date("15.06.2021"));    // -> true
bdc.isShortenedDay(Date("03.03.2021"));     // -> true
bdc.addDays(Date("01.01.2021"), 1);         // -> 02.01.2021
bdc.addWorkingDays(Date("01.01.2021"), 1);  // -> 12.01.2021
```

## Типы дней
В библиотеке определные следующие типы дней:
* 0 - Рабочий день
* 1 - Выходной день
* 2 - Нерабочий день
* 3 - Сокращенный день