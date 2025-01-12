# Диаграммы состояний


## Урок 1. Основы диаграмм состояний

> **Задание:**
> Опишите диаграмму состояния оператора центра оповещения. Кейс прикреплен в материалах к семинару: ИТ решение для города Х.
>

![Lesson-1.drawio](./Lesson-1.drawio.svg)


## Урок 2. Конечные автоматы

| **Состояние** | **Событие** | **Действие** | **Следующее состояние** |
| --- | --- | --- | --- |
| Ожидание | Обнружен дым/температура | Отправить сигнал в центр управления | Обнаружение |
| Обнаружение | Сигнал отправлен | Ожидать подтверждения от центра | Ожидание подтверждения |
| Ожидание подтверждения | Подтверждение получено | Подтвердить наличие пожара, уведомить пользователей | Подтверждено |
| Ожидание подтверждения | Подтверждение не получено | Сигнал ложный, возврат к ожиданию | Ожидание |
| Подтверждено | Пожар устранен | Сброс состояния датчиков | Сброс |
| Сброс | - | Переключиться в режим ожидания | Ожидание |

![Lesson-2.drawio](./Lesson-2.drawio.svg)


## Урок 3. Моделирование жизненного цикла объекта и введение в UML

```plantuml
@startuml
[*] --> ОжиданиеОповещения : Пользователь зарегистрирован

ОжиданиеОповещения --> ПолучениеОповещения : Получено оповещение о пожаре
ПолучениеОповещения --> ПринятиеМер : Пользователь решает вызвать пожарных или проверить здание
ПринятиеМер --> Завершение : Меры приняты, инцидент завершен

ПолучениеОповещения --> [*] : Пользователь проигнорировал оповещение
ПринятиеМер --> [*] : Пользователь не предпринял действий
@enduml
```

![plantUML](https://www.planttext.com/plantuml/svg/bL8xRW913Etd5AwZS84K4VT0AP2IZb00wScY_BH8b6aGN64530nQ3Lp1lb6UFH048WifLZlslB7Vir-zssjsUY_FBTUuUQ1QxPvumaiElE228_uUyPOtF6ClNuYGan7T4K-HB6N8Axii9CCbOaAYa3w2EP2lak4Sy1c8etDNrJSYgSD0FbBw4fKzS4C8Jt3iIVEQNIPwxihoYOcAu2WZg5JW691-rH2qWtn2efUCU2Ov47Ql0pgmY9BB6w5aoG7vtPYyZInBi_oTa_k3XH7y1ieUekbUCEWPGl9KUlTKybkoyxjj0MYbk3ekuFup7dLEbI6IhW13O3b7TYZFhgfAwQLUKJUzDVyj3ggraKfTgo7n8F3QrP_QZ_3z3m00)