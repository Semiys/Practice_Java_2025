# Практические задания по основам Java

Этот репозиторий содержит решения комплексных учебных заданий, направленных на освоение и закрепление фундаментальных и продвинутых концепций языка программирования Java. Каждое задание представляет собой отдельный мини-проект, демонстрирующий различные аспекты ООП, работы со структурами данных и современными API языка.

## Содержание
1.  [Задание 1: Основы ООП — Класс `BankAccount`](#задание-1-основы-ооп--класс-bankaccount)
2.  [Задание 2: Структуры данных и Stream API — Управление автопарком](#задание-2-структуры-данных-и-stream-api--управление-автопарком)
3.  [Задание 3: Продвинутое ООП — Система бронирования номеров](#задание-3-продвинутое-ооп--система-бронирования-номеров)
4.  [Задание 4: Функциональное программирование и Рефлексия](#задание-4-функциональное-программирование-и-рефлексия)
---

## Задание 1: Основы ООП — Класс `BankAccount`

Проект, демонстрирующий базовые принципы объектно-ориентированного программирования через создание и управление банковским счетом.

### Ключевые навыки и концепции:
*   Создание классов и объектов.
*   Конструкторы и инициализация полей.
*   Методы и логика инкапсуляции.
*   Работа с датой и временем (`LocalDateTime`).
*   Переопределение методов класса `Object` (`toString`, `equals`, `hashCode`).
*   Генерация случайных чисел (`Random`).

### Реализованный функционал:
*   **Класс `BankAccount`** со полями: `ownerName`, `balance`, `openDate`, `isLocked`.
*   **Конструктор**, который инициализирует счет с начальным балансом и генерирует уникальный 8-значный номер счета.
*   **Методы для управления счетом:**
    *   `deposit(amount)`: для пополнения счета.
    *   `withdraw(amount)`: для снятия средств с проверкой на достаточный баланс.
    *   `transfer(otherAccount, amount)`: для перевода средств на другой счет.
*   **Переопределен метод `toString()`** для удобного вывода информации о счете.
*   **Переопределены методы `equals()` и `hashCode()`** для корректного сравнения объектов счетов.

---

## Задание 2: Структуры данных и Stream API — Управление автопарком

Комплексное задание, охватывающее работу с массивами, коллекциями и Stream API для анализа и управления данными об автомобилях.

### Ключевые навыки и концепции:
*   **Массивы:** Создание, итерация, фильтрация.
*   **Коллекции:** `List`, `Set`, `HashSet`, `Map`. Удаление дубликатов, сортировка, модификация.
*   **`equals()` / `hashCode()`:** Обеспечение уникальности объектов в коллекциях по кастомному полю (VIN).
*   **`Comparable<T>`:** Реализация интерфейса для кастомной сортировки объектов.
*   **Stream API:** Фильтрация (`filter`), сортировка (`sorted`), ограничение выборки (`limit`), агрегатные операции (`average`), группировка (`groupingBy`).
*   **Интерактивное консольное приложение:** Использование `Scanner` для создания меню.

### Реализованный функционал:
1.  **Работа с массивами:**
    *   Создан массив с годами выпуска 50 случайных машин.
    *   Реализован вывод машин, выпущенных после 2015 года, и подсчет среднего возраста авто.
2.  **Работа с коллекциями:**
    *   Список моделей обработан для удаления дубликатов.
    *   Данные отсортированы в обратном алфавитном порядке.
    *   Реализована замена моделей "Tesla" на "ELECTRO_CAR".
3.  **Сравнение автомобилей:**
    *   Создан класс `Car` с полями VIN, модель, производитель и т.д.
    *   `equals()` и `hashCode()` переопределены для сравнения только по VIN, что обеспечивает уникальность машин в `HashSet`.
    *   Реализован `Comparable<Car>` для сортировки по году выпуска.
4.  **Анализ с помощью Stream API:**
    *   Реализованы фильтрация, сортировка и вывод топ-3 самых дорогих машин с пробегом менее 50 000 км.
    *   Подсчитан средний пробег всех машин.
    *   Автомобили сгруппированы по производителю в `Map<String, List<Car>>`.
5.  **Система "Автоцентр":**
    *   Создан класс `CarDealership` для управления списком машин.
    *   Реализовано интерактивное меню для вызова методов: добавление машины (с проверкой на дубликаты по VIN), поиск по производителю, расчет средней цены по типу, получение статистики и т.д.

---

## Задание 3: Продвинутое ООП — Система бронирования номеров

Проект, демонстрирующий глубокое понимание ООП, включая абстракцию, наследование, дженерики и обработку исключений на примере системы отеля.

### Ключевые навыки и концепции:
*   **Наследование и Абстракция:** Построение сложной иерархии классов с использованием `abstract class` (`Room`, `ProRoom`).
*   **Интерфейсы:** Определение контрактов для сервисного слоя (`RoomService`).
*   **Дженерики (Generics):** Использование ограниченных дженериков (`<T extends Room>`, `<T extends LuxRoom>`) для создания гибких и типобезопасных сервисов.
*   **Перечисления (Enum):** Создание `enum` с полями и методами для централизованного и безопасного управления ценами.
*   **Кастомные исключения:** Создание и использование собственного непроверяемого исключения (`RoomIsBookedException`).
*   **Разделение ответственности (SoC):** Четкое разделение "данных" (классы комнат) и "поведения" (сервисные классы).

### Реализованный функционал:
*   **Иерархия классов комнат** (`EconomyRoom`, `StandardRoom`, `LuxRoom`, `UltraLuxRoom`).
*   **Запрет на создание** экземпляров абстрактных классов `Room` и `ProRoom`.
*   **Сервисный слой:**
    *   Интерфейс `RoomService<T extends Room>` с методами `clean`, `reserve`, `free`.
    *   Класс `HotelRoomService` как основная реализация сервиса.
*   **Обработка ошибок:** При попытке забронировать занятую комнату выбрасывается `RoomIsBookedException`.
*   **Дополнительные задания:**
    *   **Цены через `enum`:** Создано перечисление `Prices`, и вся логика установки цен переведена на его использование.
    *   **Расширенный сервис:**
        *   Создан интерфейс `LuxRoomService`, который наследуется от `RoomService` и добавляет метод `foodDelivery`.
        *   Создан класс `PremiumHotelService`, реализующий новый интерфейс и работающий только с `LuxRoom` и его наследниками.
        *   В `Main` классе продемонстрирована типобезопасность системы: попытка заказать еду в `EconomyRoom` через `PremiumHotelService` приводит к ошибке компиляции.

## Задание 4: Функциональное программирование и Рефлексия

Это задание посвящено двум мощным механизмам Java: лямбда-выражениям и Reflection API. Работа разделена на две части: практическое применение стандартных функциональных интерфейсов и создание собственных аннотаций с их последующей обработкой.

### Ключевые навыки и концепции:
*   **Лямбда-выражения:** Написание анонимных функций для реализации функциональных интерфейсов.
*   **Функциональные интерфейсы:** Глубокое понимание и практическое использование:
    *   `Predicate<T>`: для создания условий и фильтрации (включая композицию с `and()` и `or()`).
    *   `Consumer<T>`: для выполнения действий над объектом (включая цепочки вызовов с `andThen()`).
    *   `Function<T, R>`: для преобразования данных из одного типа в другой.
    *   `Supplier<T>`: для генерации или поставки данных.
*   **Кастомные аннотации:** Создание собственных аннотаций с параметрами с использованием мета-аннотаций `@Retention(RUNTIME)` и `@Target`.
*   **Reflection API:**
    *   Анализ метаданных классов, методов и полей во время выполнения.
    *   Чтение аннотаций с классов и их членов (`isAnnotationPresent`, `getAnnotation`).
    *   Динамический доступ к полям объекта, включая приватные (`getDeclaredFields`, `setAccessible`, `get`).

### Реализованный функционал:
1.  **Работа с лямбда-выражениями:**
    *   Созданы и продемонстрированы лямбда-выражения для всех основных функциональных интерфейсов из пакета `java.util.function`.
    *   Реализованы проверки строк, обработка объектов и генерация данных с помощью лаконичного функционального синтаксиса.
2.  **Кастомная аннотация `@DeprecatedEx`:**
    *   Создана аннотация, имитирующая стандартную `@Deprecated`, но с обязательным сообщением об альтернативе.
    *   Написан обработчик `AnnotationProcessor`, который через рефлексию находит все помеченные классы и методы и выводит предупреждающие сообщения в консоль.
3.  **Кастомная сериализация в JSON с аннотацией `@JsonField`:**
    *   Создана аннотация `@JsonField`, позволяющая задать имя поля для JSON-вывода.
    *   Реализован класс `JsonSerializer`, который:
        *   Принимает любой объект.
        *   Через рефлексию находит все поля, помеченные `@JsonField`.
        *   **Получает доступ к `private` полям** с помощью `field.setAccessible(true)`.
        *   Извлекает значения этих полей и формирует из них корректную JSON-строку.
