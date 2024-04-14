# Опис дотримання принципів програмування

## DRY (Don't Repeat Yourself)
Принцип DRY виконується у нашому коді завдяки створенню окремих класів для різних функцій. Наприклад, класи [Money](./Lab_01/class.cs#L7-L24), [Product](class.cs#L27-L49), [Warehouse](class.cs#L52-L69) та [Reporting](class.cs#L71-L118) містять відповідні методи без дублювання коду.

## KISS (Keep It Simple, Stupid)
Принцип KISS підтримується шляхом створення класів з чіткими та простими функціями. Наприклад, методи для реєстрації надходження товару, відвантаження товару та створення звіту по інвентаризації можна знайти [тут](link_to_code).

## SOLID
### Single Responsibility Principle (Принцип єдиного обов'язку)
Кожен клас у нашій системі виконує лише одну відповідальність. Наприклад, клас [Product](link_to_code) відповідає тільки за характеристики продукту та методи для його редагування.

### Open/Closed Principle (Принцип відкритості/закритості)
Ми використовуємо принцип відкритості/закритості, створюючи класи таким чином, що вони можуть бути розширені новими функціональностями без змінювання існуючого коду. Наприклад, клас [Reporting](link_to_code) залишається закритим для змін при додаванні нового способу відвантаження товару.

### Liskov Substitution Principle (Принцип підстановки Лісков)
Класи в нашій системі можна замінити їх базовими класами без втрати функціональності. Наприклад, клас [Product](link_to_code) може бути замінений похідним класом, якщо це не порушить контракти, визначені базовим класом.

### Interface Segregation Principle (Принцип розділення інтерфейсу)
Ми розділяємо інтерфейси на дрібні, специфічні для клієнта інтерфейси, що кожен клас може реалізувати без зайвих обов'язків. Наприклад, класи [Product](link_to_code) та [Warehouse](link_to_code) мають лише ті методи, які є потрібними для їхнього функціонування.

## YAGNI (You Ain't Gonna Need It)
Принцип YAGNI виконується шляхом включення тільки необхідного функціоналу в програму. У нашому коді ми додаємо лише той функціонал, який потрібен для виконання основних завдань, таких як [реєстрація надходження товару](link_to_code), [відвантаження товару](link_to_code) та [створення звіту по інвентаризації](link_to_code).

## Composition Over Inheritance
Ми використовуємо композицію замість наслідування там, де це можливо, щоб розділити поведінку між класами та зберегти їхню зв'язаність низькою. Наприклад, клас [Reporting](link_to_code) містить список об'єктів класу `Warehouse` як складову частину, замість успадкування цієї функціональності.

## Program to Interfaces not Implementations
Ми програмуємо на інтерфейси, а не на конкретні реалізації класів. Наприклад, методи класу [Reporting](link_to_code) взаємодіють з класами `Product`, `Warehouse` тощо через їхні інтерфейси, а не конкретні реалізації.

## Fail Fast
Ми застосовуємо принцип "Fail Fast", реагуючи на помилки або неправильні вхідні дані якомога швидше, щоб уникнути подальших проблем. Наприклад, у методі `ShipItem` класу [Reporting](link_to_code), ми перевіряємо, чи існує товар на складі, і видаємо повідомлення про помилку, якщо товар не знайдено.
