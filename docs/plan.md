# Планирование

## Перечень сценариев:

Для дебетовой и кредитной карт позитивные и негативные сценарии одинаковы.

### Позитивный сценарий покупки тура.
   1. Номер карты - APPROVED (см. Приложение) / Оставшиеся поля – валидные значения. В случае прохождения теста должно появляться сообщение об одобрении банком платежа.
   
### Негативные сценарии покупки тура.
   1. "Номер карты" – DECLINED / Оставшиеся поля – валидные значения. В случае прохождения теста должно появляться сообщение об отказе банка в одобрении платежа;
   2. "Номер карты" – поле не заполнено / Оставшиеся поля – валидные значения. При попытке отправки формы, должно появляться сообщение о некорректном заполнении поля "номер карты";
   3. "Номер карты" – 16 нолей / Оставшиеся поля – валидные значения. При попытке отправки формы, должно появляться сообщение о некорректном заполнении поля "номер карты";
   4. "Номер карты" – текстовое значение / Оставшиеся поля – валидные значения. При попытке ввода текстовых символов, поле "номер карты" не должно заполняться;
   5. "Месяц" – поле не заполнено / "Номер карты" – APPROVED / Оставшиеся поля – валидные значения. При попытке отправить форму, должно появляться сообщение о некорректном заполнении поля "месяц";
   6. "Месяц" – ячейка заполнена числом большим 12 / "Номер карты" – APPROVED / Оставшиеся поля – валидные значения. При попытке отправить форму, должно появляться сообщение о некорректном заполнении поля "месяц";
   7. "Месяц" – текстовое значение / "Номер карты" – APPROVED / Оставшиеся поля – валидные значения. При попытке ввода текстовых символов, поле "месяц" не должно заполняться;
   8. "Год" – поле не заполнено / "Номер карты" – APPROVED / Оставшиеся поля – валидные значения. При попытке отправить форму, должно появляться сообщение о некорректном заполнении поля "год";
   9. "Год" – двузначное число, меньше границы действия карты / "Номер карты" – APPROVED / Оставшиеся поля – валидные значения. При попытке отправить форму, должно появляться сообщение о некорректном заполнении поля "год";
   10. "Год" – текстовое значение / "Номер карты" – APPROVED / Оставшиеся поля – валидные значения. При попытке ввода текстовых символов, поле "год" не должно заполняться;
   11. "Владелец" – поле не заполнено / "Номер карты" – APPROVED / Оставшиеся поля – валидные значения. При попытке отправить форму, должно появляться сообщение о некорректном заполнении поля "владелец";
   12. "Владелец" – числовое значение / "Номер карты" – APPROVED / Оставшиеся поля – валидные значения. При попытке ввода числовых символов, поле "владелец" не должно заполняться;
   13. "Владелец" – текст на кириллице / "Номер карты" – APPROVED / Оставшиеся поля – валидные значения. При попытке ввода символов кириллицы, поле "владелец" не должно заполняться;
   14. "CVC/CVV" – поле не заполнено / "Номер карты" – APPROVED / Оставшиеся поля – валидные значения. При попытке отправить форму, должно появляться сообщение о некорректном заполнении поля "CVC/CVV";
   15. "CVC/CVV" – двузначное число / "Номер карты" – APPROVED / Оставшиеся поля – валидные значения. При попытке отправить форму, должно появляться сообщение о некорректном заполнении поля "CVC/CVV";
   16. "CVC/CVV" – четырехзначное число / "Номер карты" – APPROVED / Оставшиеся поля – валидные значения. При попытке ввода четырехзначного числа, поле "CVC/CVV" должно принимать на ввод только 3 первых значения;
   17. "CVC/CVV" – текстовое значение / "Номер карты" – APPROVED / Оставшиеся поля – валидные значения. При попытке ввода текстовых символов, поле "CVC/CVV" не должно заполняться.


### Сценарии проверки работы с базой данных:
   1. Сформировать запрос к таблице "credit_request_entity" и выбрать ячейки со статусом "APPROVED". Посчитать их общее количество;
   2. Сформировать запрос к таблице "payment_entity" и выбрать ячейки со статусом "DECLINED". Посчитать их общее количество.


## Инструменты:
- IDE: IntelliJ IDEA
- Система сборки: Gradle;
- Тестирование: JUnit5;
- Тестирование API: Rest-Assured;
- Работа с браузером: Selenide;
- Работа с базой данных: MySQL;
- Подключение базы данных: Docker;
- Система репортинга: Allure.


## Возможные риски при автоматизации
- Могут возникнут проблемы с совместимостью между двумя базами данныхь(MySQL и PostgreSQL)
- Существует риск обнаружения новых багов при подключение реальной системы ведь сейчас тестирование банковского сервиса проходило на заглушке.
- Проведенное тестирование станет не актуальным, если структура запросов со стороны банка будет меняться. 

## Оценка затрат времени с учётом непредвиденных обстоятельств (в часах)
~50 часов

## План проведения и сдачи работ:

Проведение тестирования и отчет по итогам тестирования – 18.01.2023 – 23.01.2023

Отчет по итогам автоматизации – 25.01.2023

## Приложение
### Предоставленные номера карт для тестирования
- 1111 2222 3333 4444 – APPROVED карта (операция должна быть одобрена);
- 9999 8888 7777 6666 – DECLINED карта (операция должна быть отклонена).