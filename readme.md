# Тема 11. Итераторы и генераторы
Отчет по Теме #11 выполнил(а):
- Ковалева Ксения Сергеевна
- АИС-21-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | 
| Задание 4 | + | 
| Задание 5 | + | 


знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №11
### 1. Простой итератор, но у него нет гибкой настройки, например его нельзя развернуть. Он работает просто как next(), но нет prev()

```python
numbers = [0,1,2,3,4,5]
for item in numbers:
    print(item)
```
### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/7f2209bc-f38d-4585-b6ca-0b6925591b52)


### 2. Класс итератор с гибкой настройкой и удобным применением.

```python
class CountDown:
    def init(self, start):
        self.count = start + 1

    def iter(self):
        return self

    def next(self):
        self.count -=1
        if self.count < 0:
            raise StopIteration
        return self.count

if name== "main":
    counter = CountDown(5)
    for i in counter:
        print(i)
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/76c3a3ec-7e4a-42e9-8f15-a33df369bef5)



### 3. Генератор списка
```python
a = [i**2 for i in range(1,5)]

print('a-', a)
for i in a:
    print(i)

print('iter(a) -', iter(a))
for i in a:
    print(i)
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/4922f421-f930-45ac-a93e-3a45fb26712e)


### 4. Выражения генераторы

```python
b = (i**2 for i in range(1,5))
print(b)
print('first')
for i in b:
    print(i)
print('second')

for i in b:
    print(i)
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/9c546f12-1a4c-49b8-a7b9-9ed0cf127abe)


### 5. Такой же счетчик, как и в первом задании, только это генератор и использует yield

```python
def countdown(count):
    while count>=0:
        yield count
        count -=1

if name== 'main':
    counter = countdown(5)
    for i in counter:
        print(i)
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/0d79b7c4-ca05-4d06-b737-0855efaf9740)




## Самостоятельная работа №11

### 1.  Вас никак не могут оставить числа Фибоначчи, очень уж они вас заинтересовали. Изучив новые возможности Python вы решили реализовать программу, которая считает числа Фибоначчи при помощи итераторов. Расчет начинается с чисел 1 и 1. Создайте функцию fib(n), генерирующую n чисел Фибоначчи с минимальными затратами ресурсов. Для реализации этой функции потребуется обратиться к инструкции yield ( Она не сохраняет в оперативной памяти огромную последовательность, а дает возможность "доставать" промежуточные результаты по одному). Результатом решения задачи будет листинг кода и вывод в консоль с числом Фибоначчи от 200

```python
def fib(n):
    a, b = 1, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

# Вывод чисел Фибоначчи до 200
for num in fib(200):
    print(num)
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/b76a96e4-1114-4d60-ae18-04a76c468e26)


### 2. К коду предыдущей задачи добавьте запоминание каждого числа Фибоначчи в файл "fib.txt", при этом каждое число должно находиться на отдельной строчке. Результатом выполнения задачи будет листинг кода и скриншот получившегося файла

```python
def fib(n):
    a, b = 1, 1
    with open("fib.txt", "w") as file:
        for _ in range(n):
            file.write(str(a) + "\n")
            a, b = b, a + b

# Вывод чисел Фибоначчи до 200
for num in fib(200):
    print(num)
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/9c4e4874-c411-4e04-9451-7b114f5c832a)


## Вывод.
#### Спасибо большое за этот замечательный курс, наконец-то я что-то поняла и выучила впервые за 3 курса!!!
![image](https://github.com/XenKov21/prob/assets/145853363/e32e96d1-84b3-41b1-b279-39038b146755)
