iOS. Лабораторные работы 1,2
=============================

#Задание
Грубая симуляция пищевой цепочки леса. Лесная флора и фауна: хищники, травоядные, трава, мусор. Нужно реализовать их иерархию и взаимоотношения с помощью классов и протоколов. Переопределить метод description для вывода в лог информации о созданных объектах.


**Этап 1:** Построение иерархии
- Травоядное может слопать только траву. Хищники траву не едят.
- Травоядное может прятаться (от хищников). Хищник может защищаться (от других хищников). "прячется" и "защищается" возвращает рандомное YES или NO.
- Хищник может слопать травоядное, если оно не прячется.
- Хищник может слопать другого хищника, если его вес не превышает вес первого и он не защищается.
- <font color="red">Травоядные и хищники могут поедать мусор. У мусора нет названия, но есть отрицательная калорийность.</font>
- Хищник в начале жизни получает 100 единиц собственных калорий, травоядное - 50, трава - 10.
- От съеденной еды (кроме мусора) хищник получает к своим калориям половину калорий еды-жертвы.
- От съеденной еды (кроме мусора) травоядное получает к своим калориям все калории еды-жертвы.
- <font color="red">От съеденного мусора хищники и травоядные получают -1 калорию.</font>


**Этап 2:** симуляция жизни
- Общий лес (синглтон) в начале работы программы заполняется травами с произвольными названиями, хищниками с произвольными названиями и весом, травоядными с произвольным названием, <font color="red">мусором без названия</font>, все объекты помещаются в "жителиЛеса". Должен быть как минимум один хищник.
- "симулироватьДень" симулирует обычный день в обычном лесу - произвольное животное пытается съесть другой произвольный объект в лесу. В случае успеха объект пропадает из леса, помещается в желудок животному и хранится до конца работы программы.
- Взаимоотношения объектов (кто кого может съесть) определяются в сущности “ПравилаЖизни”.
- Симуляция жизни леса происходит до тех пор пока не останется единственный хищник.
 
**Бонус:** Вывести в консоль содержимое желудка последнего хищника рекурсивно.

