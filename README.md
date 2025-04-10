Зауваження до початкового коду

1. Назви класів і змінних

Клас humanIMB має назву, яка не відповідає Java-конвенціям: слід використовувати PascalCase для назв класів, тобто HumanBMI.

Назви змінних W, H, imb повинні бути більш описовими (наприклад: weight, height, bmi).

2. Статичне поле BMI

Поле imb зроблено статичним, що є некоректним, адже кожна людина повинна мати своє значення BMI, а не спільне для всіх об'єктів класу.

3. Дублювання обчислень BMI

BMI перераховується при кожній зміні weight або height, що неефективно і порушує принцип розділення відповідальностей. Краще обчислювати BMI тоді, коли це потрібно (on-demand).

4. Невдале використання умовних операторів

Вирази типу if (imb >=18.5 & imb <25) використовують побітовий оператор &, замість логічного &&. Це потенційно небезпечно і некоректно.

5. Погане форматування та відсутність валідації

Висота не перевіряється на те, що вона не дорівнює 0 або не є від’ємною. Це може призвести до ArithmeticException.

Клас містить зайві методи, які дублюють доступ до полів (наприклад takeW замість getWeight).

6. Порушення принципу інкапсуляції

Поля класу мають публічний доступ (public double W;) — це порушення принципу інкапсуляції. Потрібно використовувати private.

7. Читабельність

Код має слабку читаємість неструктурований коментар, немає документації методів.

Зміни в рефакторингу

Перейменовано клас на HumanBMI.

Змінено імена змінних на описові.

Видалено статичне поле BMI.

Всі поля оголошено private.

Додано метод calculateBMI() для обчислення ІМТ при потребі.

Валідація параметру height (не може бути 0 або менше).

Поліпшено читабельність і стиль відповідно до Java Code Conventions.
