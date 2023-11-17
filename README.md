# Тема 8. Основы объектно-ориентированного программирования
Отчет по Теме #8 выполнил(а):
- Ковалева Ксения Сергеевна
- АИС-21-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |


знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №8
### 1. Создайте класс "Car" с атрибутами производитель и модель. Создайте объект класса. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями

```python
#Создаем класс "Car"
class Car:
#Определяем атрибуты производитель и модель
    def init(self, make, model):
        self.make = make #Присваеваем производителя объекту
        self.model = model #Присваеваем модель объекту
# Создаем объект класса "Car" c производителем "Toyota" и моделью "Corolla"
my_car = (Car('Toyta', 'Corolla')) # Создаем объект my_car класса "Car" с указананными атрибутами
```

### 2. Дополните код из первого задания, добавив в него атрибуты и методы класса, заставьте машину "поехать". Напишите  комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль

```python
#Создаем класс "Car"
class Car:
#Определяем атрибуты производитель и модель
    def init(self, make, model):
        self.make = make #Присваеваем производителя объекту
        self.model = model #Присваеваем модель объекту

    def drive(self): # Определяем метод drive
        print(f"Driving the {self.make} {self.model}") # Выводим сообщение о том, что мы ведем машину указанной марки и модели
# Создаем объект класса "Car" c производителем "Toyota" и моделью "Corolla"
my_car = Car('Toyta', 'Corolla') # Создаем объект my_car класса "Car" с указананными атрибутами
my_car.drive() # вызываем метод drive для экземпляра my_car
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/8befd43c-5a76-477d-b160-488009a69c1d)


### 3. Создайте новый класс "ElectricCar" с методом "charge" и атрибутом емкость батареи. Реализуйте его наследование от класса, созданного в первом задании. Заставьте машину поехать, а потом заряжаться. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
#Создаем класс "Car"
class Car:
#Определяем атрибуты производитель и модель
    def init(self, make, model):
        self.make = make #Присваеваем производителя объекту
        self.model = model #Присваеваем модель объекту

    def drive(self): # Определяем метод drive
        print(f"Driving the {self.make} {self.model}") # Выводим сообщение о том, что мы ведем машину указанной марки и модели
# Создаем объект класса "Car" c производителем "Toyota" и моделью "Corolla"
my_car = Car('Toyta', 'Corolla') # Создаем объект my_car класса "Car" с указананными атрибутами
my_car.drive() # вызываем метод drive для экземпляра my_car

class ElectricCar(Car): #  конструкторе класса ElectricCar вызывается конструктор родительского класса Car с помощью super() и добавляется атрибут battery_capacity.
    def init(self, make,model,battery_capacity):
        super().init(make,model)
        self.battery_capacity = battery_capacity
    def charge(self):
        print(f'Charging the {self.make} {self.model} with {self.battery_capacity} kWh')

#Создается экземпляр my_electric_car класса ElectricCar с параметрами 'Tesla', 'Model S', 75.
my_electric_car = ElectricCar('Tesla', 'Model S', 75)
# Вызывается метод drive() для экземпляра my_electric_car, который выводит информацию о том, что машина едет.
my_electric_car.drive()
#Вызывается метод charge() для экземпляра my_electric_car, который выводит информацию о зарядке машины.
my_electric_car.charge()
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/4f983c07-17e6-445b-b9b1-f7d0f45f9423)


### 4. Реализуйте инкапсуляцию для класса, созданного в первом задании. Создайте защищенный атрибут производителя и приватный атрибут модели. Вызовите защищенный атрибут и заставьте машину поехать. Напишите комментарии для кода, объясняющие его работу.  Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
class Car:

    def init(self, make, model):
        self._make = make #Защищенный атрибут
        self.__model = model #Приватный атрибут

    def drive(self):
        print(f"Driving the {self._make} {self.__model}")
my_car = Car('Toyta', 'Corolla')
print(my_car._make) # Доступ к защищенному атрибуту
my_car.drive() # Вызов метода drive для экземпляра my_car, который выводит информацию о том, что машина едет
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/9f4610a1-2e50-4594-ba8c-44a490527807)


### 5. Реализуйте полиморфизм создав основной (общий) класс "Shape", а также еще два класса "Rectangle" и "Circle". Внутри последних двух классов реализуйте методы для подсчета площади фигуры. После этого создайте массив с фигурами, поместите туда круг и прямоугольник, затем при помощи цикла выведите их площади. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
# Определение общего класса Shape
class Shape:
    def area(self):
        pass

# Определение класса Rectangle, унаследованного от Shape
class Rectangle(Shape):
    def init(self, width, height):
        self.width = width
        self.height = height
# Метод для подсчета плдощади прямоугольника
    def area(self):
        return self.width * self.height

#Определение класса Circle, унаследованного от Shape
class Circle(Shape):
    def init(self, radius):
        self.radius = radius
# Метод для подсчета площади круга
    def area(self):
        return 3.14 * self.radius * self.radius
# Создание экземпляров классов Rectangle и Circle
rectangle = Rectangle(2, 10)
circle = Circle(7)

# Помещение фигур в массив
shapes = [rectangle, circle]

# Вывод площади каждой фигуры в массиве
for shape in shapes:
    print(shape.area())
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/094b0669-5e75-42c4-9356-6fc144ab90b7)



## Самостоятельная работа №8

### 1,2. Самостоятельно создайте класс и его объект.Самостоятельно создайте атрибуты и методы для ранее созданного класса.

```python
class Animal:
    def init(self, name):
        self.name = name

    def sound(self):
        pass


class Dog(Animal):
    def sound(self):
        return "Гав-гав!"


class Cat(Animal):
    def sound(self):
        return "Мяу!"


# Создание объектов классов
dog = Dog("Пёс")
cat = Cat("Котька")

# Вывод звука каждого животного
print(f"{dog.name} говорит: {dog.sound()}")
print(f"{cat.name} говорит: {cat.sound()}")
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/1ff5417b-d551-447f-9b58-336370d898ca)


### 3. Самостоятельно реализуйте наследование

```python
class Animal:
    def init(self, name):
        self.name = name

    def sound(self):
        pass


class Dog(Animal):
    def sound(self):
        return "Гав-гав!"


class Cat(Animal):
    def sound(self):
        return "Мяу!"


class Bird(Animal):
    def sound(self):
        return "Кыщ-Кыщ!"


# Создание объектов классов
dog = Dog("Пёс")
cat = Cat("Котька")
bird = Bird("Птичка")

# Вывод звука каждого животного
print(f"{dog.name} говорит: {dog.sound()}")
print(f"{cat.name} говорит: {cat.sound()}")
print(f"{bird.name} говорит: {bird.sound()}")
```

### Результат.
####  Я использовала наследование, чтобы классы-потомки унаследовали атрибут name и метод sound от класса Animal. Каждый класс-потомок переопределил метод sound с уникальным звуком для каждого животного
![image](https://github.com/XenKov21/prob/assets/145853363/ba5e80a6-226d-4abd-a8b4-60f6686efbda)


### 4. Самостоятельно реализуйте инкапсуляцию

```python
class Animal:
    def init(self, name):
        self._name = name  # Используем одиночное подчеркивание для обозначения "protected" атрибута

    def sound(self):
        pass

    def get_name(self):
        return self._name

    def set_name(self, new_name):
        self._name = new_name


class Dog(Animal):
    def sound(self):
        return "Гав-гав!"


class Cat(Animal):
    def sound(self):
        return "Мяу!"


# Создание объектов классов
dog = Dog("Пёс")
cat = Cat("Котька")

# Вывод звука и имени каждого животного
print(f"{dog.get_name()} говорит: {dog.sound()}")
print(f"{cat.get_name()} говорит: {cat.sound()}")

# Изменение имени животного
cat.set_name("Котяра")
print(f"{cat.get_name()} говорит: {cat.sound()}")
```

### Результат.
#### В этом примере я использовала инкапсуляцию, чтобы скрыть атрибут _name внутри класса Animal, используя одиночное подчеркивание. Мы предоставили методы get_name и set_name, чтобы получить и установить значение этого атрибута
![image](https://github.com/XenKov21/prob/assets/145853363/0467ffeb-c9e3-4cba-9e70-50fb349c6ddd)


### 5. Самостоятельно реализуйте полиморфизм

### Результат. 
####  С самого начала в моем классе был полиморфизм.


## Вывод.
#### Спасибо, я снова почувствовала себя молоденькой 2 курсницей, которая писала курсовую по ооп. Спасибо за объяснение, вновь вспомнила моменты, которые забылись.
![image](https://github.com/XenKov21/prob/assets/145853363/560ca30b-04e2-48fc-ba1c-ee8db7e9ea1a)


