# Тема 5. Базовые коллекции: строки и списки
Отчет по Теме #5 выполнил(а):
- Ковалева Ксения Сергеевна
- АИС-21-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |
| Задание 6 | + | 
| Задание 7 | + | 
| Задание 8 | + | 
| Задание 9 | + |
| Задание 10 | + | 

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №5
### 1. Друзья предложили вам поиграть в игру "найди отличия и убери повторения (версия для программистов)". Суть игры состоит в том, что на вход программы поступает два множества, а ваша задача вывести все элементы первого, которых нет во втором.  А вы как раз недавно прошли множества и знаете их возможности, поэтому это не составит для вас труда

```python
set_1 = {'White', 'Black', 'Red', 'Pink'}
set_2 = {'Red', 'Green', 'Blue', 'Red'}

print(set_1 - set_2)
```
### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/da37022a-38a3-48a5-8586-9dbc082cb379)

#### Пример с разными видами повторений.
```python
set_1 = {'White', 'Black', 'Red', 'Pink'}
set_2 = {'Red', 'Green', 'Blue', 'Red'}
print('1', set_1 - set_2)

set_1 = {'White', 'Black', 'Red', 'Pink', 'White', 'Black', }
set_2 = {'Red', 'Green', 'Blue', 'Red'}
print('2', set_1 - set_2)

set_1 = {'White', 'Black', 'Red', 'Pink', 'Black', 'Red', 'Pink'}
set_2 = {'Red', 'Green', 'Blue', 'Red'}
print('3', set_1 - set_2)
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/b74bb282-c9d8-418b-8103-801bb3384250)


### 2. Напишите две одинаковые программы, только одна будет использовать set(), а вторая frozenset() и попробуйте к исходному множеству добавить несколько элементов, например, через цикл.  Вариант с set()

```python
a = set('abcdefg')
print(a)
for i in range(1,5):
    a.add(i)
print(a)
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/bc4d7174-db5b-4937-a8da-3edac2d27b4b)

#### Вариант с frozenset()

```python
a = frozenset('abcdefg')
print(a)
for i in range(1,5):
    a.add(i)
print(a)
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/d048ca3a-8c71-4bfd-95b1-863bb84d8b5a)

### 3.  На вход в программу поступает список (минимальной длинной 2 символа). Напишите программу, которая будет менять первый и последний элемент списка

```python
def replace(input_list):
    memory = input_list[0]
    input_list[0] = input_list[-1]
    input_list[-1] = memory

    return input_list

print(replace([1,2,3,4,5]))
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/b7f8162e-6510-4a0e-bdfa-294aa4146b75)

### 4. На вход в программу поступает список( минимальный длинной 10 символов). Напишите программу, которая выводит элементы с индексами от 2 до 6. В программе необходимо использовать "срез"

```python
a = [12, 54, 32, 57, 843, 2346, 765, 75, 25, 234, 756, 23]
print (a[2:6])
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/d5b882b6-b587-40fd-b3b2-f9baffb7f69c)

### 5. Иван задумался о поиске "бесполезного" числа, полученного из списка. Суть поиска в следующем: он берет произвольный список чисел, находит самое большое из них, а затем делит его на длину списка. Студент пока не придумал, где может пригодиться подобное значение, но ищет у вас помощи в реализации такой функции useless()

```python
def useless(lst):
    return max(lst) / len(lst)
print(useless([3,5,7,3,33]))
print(useless([-12.5, 54, 77.3, 0, -36, 98.2, - 63, 21.7, 47, -89.6]))
print(useless([-25.8, 86, 12.5, -56, 73.2,0, 43, -91.5,65.9, -7]))
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/989ab933-8f24-4343-afe0-659a20588c78)

### 6. Ребята не могут определится каким супергероем они хотят стать. У них есть случайно составленный список супергероев, и вы должны определить кто из ребят будет каким супергероем. Необходимо использовать разделение списков.

```python
superheroes = ['superman', 'spiderman', 'batman']
nikolay, vasiliy, ivan = superheroes

print('Николай - ', nikolay)
print('Василий - ', vasiliy)
print('Иван - ', ivan)
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/e10773ab-d0c7-488e-803b-22fddc9e652a)

### 7.Вововчка, насмотревшись передачи "Слабое звено" решил написатьь программу, которая также будет находить самое слабое звено (минимальный элемент) и удалять его, только делать он это хочет не с людьми, а со списком. Помогите Вовочке с реализацией программы.

```python
a = [-25.8, 86, 12.5, -56, 73.2, 0, 43, -91.5, 65.9, -7]
a.sort()
print('Отсортированный список:\n', a)
a.pop(0)
print('Отсортированный список без наименьшего элемента:\n', a)
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/198fd699-c98a-4997-9377-e61cd6899647)

### 8. Михаил решил создать большой n-мерный список, для этого он случайным образом создал несколько списков, состоящих минимум из 3, а максимум из 10 элементов и поместил их в один большой список. Он также как и Иван не знает зачем ему это сейчас нужно, но надеется на то что это пригодится ему в будущем.

```python
from random import randint

def list_maker():
    a = [randint(1,100)] * randint(3,10)
    return a

if __name__== '__main__':
    result = []
    for i in range(randint(1,5)):
        result.append(list_maker())

    print(result)
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/95a90c41-1221-42c8-af57-834c23c8ac64)

### 9. Вы работаете в ресторане и отвечает за статистику покупок, ваша задача сравнить между собой заказы покупателей, которые указаны в разном порядке. Реализуйте функцию superset(), которая принимает 2 множества. Результат работы функции: вывод в консоль одно их сообщений в зависимости от ситуации:
1-"Супермножество не обнаружено"
2-"Объект {X} является чистым супермножеством"
3 - "Множества равны"

```python
def superset(set_1,set_2):
    if set_1 > set_2:
        print(f'Объект {set_1} является чистым супермножеством')
    elif set_1 == set_2:
        print(f"Множества равны")
    elif set_1 < set_2:
        print(f'Объект {set_2} является чистым супермножеством')
    else:
        print('Супермножество не обнаружено')

if name == 'main':
    superset({1,8,3,5},{3,5})
    superset({1,8,3,5},{5,3,8,1})
    superset({3,5}, {5,3,8,1})
    superset({90,100},{3,5})
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/d307ada4-a29e-4bc6-954b-cc925073d22c)

### 10. Предположим, что вам нужно разобрать стопку бумаг, но нужно начать работу с нижней, "переверните стопку". Вам дан произвольный список. Представьте его в обратном порядке. Программа должна занимать не более двух строк в редакторе кода.

```python
my_list = [2,5,8,3]
print(my_list[::-1])
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/bfad1abd-6e1a-440b-9601-73c3369362c8)

## Самостоятельная работа №5

### 1. Ресторан на предприятии ведет учет посещений за неделю при помощи кода работника. У них есть список со всеми посещениями за неделю. Ваша задача посчитать:
- Сколько было выдано чеков
- Сколько разных людей посетило ресторан
- Какой работник посетил ресторан больше всех раз

```python
lst = [8734, 2345, 8201, 6621, 9999, 1234, 5678, 8201, 8888, 4321, 3365,
    1478, 9865, 5555, 7777, 9998, 1111, 2222, 3333, 4444, 5556, 6666,
    5410, 7778, 8889, 4445, 1439, 9604, 8201, 3365, 7502, 3016, 4928,
    5837, 8201, 2643, 5017, 9682, 8530, 3250, 7193, 9051, 4506, 1987,
    3365, 5410, 7168, 7777, 9865, 5678, 8201, 4445, 3016, 4506, 4506]

#Создаём словарь (пары данных по типу "ключ" : "значение"
d = {}
#Прошли по массиву данных. Если встречаем число которого ещё не было в словаре, то добавляем его, иначе - увеличиваем значение.
for i in lst:
    if i in d:
        d[i] += 1
    else:
        d[i] = 1

#для получения "всего чеков" черем длину листа
print("Всего было выдано {} чеков" .format(len(lst)))
#для получения количества уникальных посетителей берем длину словаря
print("Эти чеки выдали {} уникальному гостю" .format(len(d)))
#для получения ключа с наибольшим значением ищем max по значениям
print("Чаще всего приходил гость, получающий чеки №{}" .format(max(d, key=d.get)))
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/c5dc2bf4-e885-47d4-afc9-10e74d2d886b)

### 2. На физкультуре студенты сдавали бег, у преподавателя физкультуры есть список всех результатов, ему нужно узнать:
-Три лучшие результата
- Три худшие результата
-Все результаты начиная с 10
Ваша задача помочь ему в этом.

```python
#сортируем массив по возрастанию времени, получая в качестве первых элементов лучшее время
def threebest (lst):
    lst.sort()
    return(lst[0], lst[1], lst[2])
#аналогично прошлому, но в этот раз переворачивает список чтобы на первых местах были наибольшеи числа (худшие результаты).
#инверсия выводимых чисел чтобы выглядело красивее
def threeworst (lst):
    lst.sort(reverse=True)
    return(lst[2], lst[1], lst[0])

#обрезаем массив по условию (начинается с элемента 9:не работать с элемента номер длина массива:с шагом 1)
#создаём пустую строку для работы
#к строке прибавляем каждый элемент обрезка по очереди, а так же запятую и пробел чтобы прасиво было
#вообще для этого есть функция join, но у меня она не захотела работать с float'ом
#т.к. каждый раз в конце мы добавляли запятую и пробел, они стоят в конце, поэтому с помощью форматирования [:-кол-во элементов с конца] избавляюсь от лишнего
def transform (lst):
    minustenlst = lst[9:len(lst):1]
    string = ""
    for i in minustenlst:
        string += (str(i) + ", ")
    return(string[:-2])

lst = [10.2, 14.8, 19.3, 22.7, 12.5, 33.1, 38.9, 21.6, 26.4, 17.1, 30.2, 35.7, 16.9, 27.8, 24.5, 16.3, 18.7, 31.9, 12.9, 37.4]

a,b,c = threebest(lst)
print("Три лучших результата: {}, {}, {}." .format(a,b,c))
a,b,c = threeworst(lst)
print("Три худших результата: {}, {}, {}." .format(a,b,c))
string = transform(lst)
print("список всех значения больше 10 - просто вывод массива, так что вывод массива начиная с 10 элемента: {}." .format(string))
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/5a917bb8-46ac-41ee-a8bc-bb56f5ae85b8)

### 3. Преподаватель по математике придумал странную задачку. У вас есть три списка с элементами, каждый элемент которых - длина стороны треугольника, ваша задача найти площади двух треугольников, составленные из максимальных и минимальных элементов полученных списков.

```python
#для использования sqrt (корень) добавляю библиотеку math. 
import math
#нахожу минимальные значения в массивах и через свой массив выпускаю их дальше
def minsides (one,two,three):
    a = [0, 0, 0]
    a[0], a[1], a[2] = min(one), min(two), min(three)
    return(a)
#нахожу максимальные значения в массивах и через свой массив выпускаю их дальше
def maxsides (one,two,three):
    a = [0, 0, 0]
    a[0], a[1], a[2] = max(one), max(two), max(three)
    return(a)
#получая на вход массив данных считаю площадь через полупериметр
def triangleArea(lst):
    hp=sum(lst)/2
    area = math.sqrt(hp*(hp-lst[0])*(hp-lst[1])*(hp-lst[2]))
    return area

one =[12, 25, 3, 48, 71]
two =[5, 18, 40, 62, 98]
three = [4, 21, 37, 56, 84]

print("Площадь треугольника по меньшим сторонам = {}" .format(triangleArea(minsides(one, two, three))))
print("Площадь треугольника по бо́льшим сторонам = {}" .format(round(triangleArea(maxsides(one, two, three)),2)))
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/84ffd6de-68a9-4ac1-ada9-83117794f25f)

### 4. Никто не любит получать плохие оценки, поэтому Борис решил это исправить. Допустим, что все оценки студента за семестр хранятся в одном списке. Ваша задача удалить из этого списка все двойки , а все тройки заменить на четверки.

```python
def newGrades (grades):
    while 2 in grades:
        grades.remove(2)
    grades = [4 if x == 3 else x for x in grades]
    return(grades)

def transform (lst):
    string = ""
    for i in lst:
        string += (str(i) + ", ")
    return(string[:-2])

grades1 = [2, 3, 4, 5, 3, 4, 5, 2, 2, 5, 3, 4, 3, 5, 4]
grades2 = [4, 2, 3, 5, 3, 5, 4, 2, 2, 5, 4, 3, 5, 3, 4]
grades3 = [5, 4, 3, 3, 4, 3, 3, 5, 5, 3, 3, 3, 3, 4, 4]

grades = newGrades(grades1)
print("Оценки Бориса из первого списка: {}" .format(transform(grades)))
grades = newGrades(grades2)
print("Оценки Бориса из второго списка: {}" .format(transform(grades)))
grades = newGrades(grades2)
print("Оценки Бориса из третьего списка: {}" .format(transform(grades)))
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/790a15c2-081d-4768-adb9-ee42548f6f49)

### 5. Вам предоставлены списки натуральных чисел, из них необходимо сформировать множества. При этом следует соблюдать это правило: если какое-либо число повторяется, то преобразовать его в строку по следующему образцу: например, если число 4 повторяется 3 раза, то в множестве будет следующая записать: само число 4, строка "44", строка "444"
```python
def somestrange(d):
    sett = set()
    for i in d:
        sett.add(i)
        for j in range(2, d[i] + 1):
            sett.add(str(i) * j)
    return(sett)
def createdict(lst):
    d = {}
    for i in lst:
        if i in d:
            d[i] += 1
        else:
            d[i] = 1
    return(d)

list_1 = [1, 1, 3, 3, 1]
list_2 = [5, 5, 5, 5, 5, 5, 5]
list_3 = [2, 2, 1, 2, 2, 5, 6, 7, 1, 3, 2, 2]

set_1 = somestrange(createdict(list_1))
set_2 = somestrange(createdict(list_2))
set_3 = somestrange(createdict(list_3))
print(set_1)
print(set_2)
print(set_3)
```

### Результат.  
![image](https://github.com/XenKov21/prob/assets/145853363/472b50d5-ff3a-426a-a558-1540c2c68895)

## Вывод.
#### Благодарю вас за теорию! Я долго не понимала в чем различия кортежей и списков, но после выполнения этой темы все стало на свои места. Очень классная формулировка заданий для самостоятельной работы. Хочется отметить, что вся теория была по делу и без лишней "воды". 
![image](https://github.com/XenKov21/prob/assets/145853363/c79b734a-6105-4a3d-92ca-68f7790adc10)
