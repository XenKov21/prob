# Тема 7. Работа с файлами (ввод, вывод)
Отчет по Теме #7 выполнил(а):
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

## Лабораторная работа №7
### 1. Составьте текстовый файл и положите его в одну директорию с программой на Python. Текстовый файл должен состоять минимум из двух строк

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/cc9eac93-5e67-450b-848e-07e0592c46c7)


### 2. Напишите программу, которая выведет только первую строку из вашего файла, при этом используйте конструкцию open()/close()


### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/8ecd9386-f581-4fb4-9bba-b3a09c370f00)



### 3. Напишите программу, которая выведет все строки из вашего файла в массиве, при этом используйте конструкцию open()/close()
```python
f = open('proba.txt', 'r')
print(f.readlines())
f.close()
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/6d2a0d83-0d1c-4e06-8908-7337e9e0fe34)


### 4. Напишите программу, которая выведет все строки из вашего файла в массиве, при этом используйте конструкцию with open()

```python
with open('proba.txt') as f:
    print(f.readlines())
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/4151f130-a202-4bda-aad0-934e7f42dfff)


### 5. Напишите программу, которая выведет каждую строку из вашего файла отдельно, при этом используйте конструкцию with open()

```python
with open('proba.txt') as f:
    for line in f:
        print(line)
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/27a7d0ee-577b-44d5-bdf7-ff1393b0ab60)


### 6. Напишите программу, которая будет добавлять новую строку в ваш файл, а потом выведет полученный файл в консоль. Вывод можно осуществлять любым способом. Обязательно проверьте сам файл, чтобы изменения в нем тоже отображались
```python
with open('proba.txt', 'a+') as f:
    f.write('\nIm additional line')
with open('proba.txt', 'r') as f:
    result = f.readlines()
    print(result)
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/b7bb3532-5260-49b9-8d3d-ad6e0292abfc)



### 7. Напишите программу, которая перепишет всю информацию, которая была у вас в файле до этого, например любые данные из произвольно вами составленного списка. Также не забудьте проверить что измененная вами информация сохранилась в файле
```python
lines = ['one', 'two', 'three']
with open('proba.txt', 'w') as f:
    for line in lines:
        f.write('\nCycle run'+line)
    print('Done!')
```

### Результат. 
#### До:
![image](https://github.com/XenKov21/prob/assets/145853363/aa701f6e-86b5-4fca-bfc4-9553490098bb)

#### После:
![image](https://github.com/XenKov21/prob/assets/145853363/de5dc8e1-668c-42ca-82f6-a1cec91dffd0)

#### Сам результат:
![image](https://github.com/XenKov21/prob/assets/145853363/d4ce30bc-5c1b-4f6b-9654-5a9d47f06f58)


### 8.  Выберите любую папку на своем компьютере, имеющую вложенные директории. Выведите на печать в терминал ее содержимое, как и всех подкаталогов при помощи функции print_docs(directory)

```python
import os

def print_docs(directory):
    all_files = os.walk(directory)
    for catalog in all_files:
        print(f'Папка {catalog[0]} содержит: ')
    print(f'Директории: {", ".join([folder for folder in catalog[1]])}')
    print(f'Файлы: {", ".join([file for file in catalog[2]])}')
    print('-' * 40)

print_docs('/Users/m0che/Desktop/фото/2021')
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/2fbe4637-7650-4673-bebf-40e1afe483a0)


### 9. Требуется реализовать функцию, которая выводит слово, имеющее максимальную длину ( или список слов, если таковых несколько)


```python
def longest_words(file):
    with open(file, encoding='utf-8') as f:
        words = f.read().split()
        max_length = len(max(words, key=len))
        for word in words:
            if len(word)== max_length:
                sought_words=word
        if len(sought_words) == 1:
            return sought_words[0]
        return sought_words
print(longest_words('proba.txt'))
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/138eed39-04bd-49ee-9698-650cace421c8)


### 10.  Требуется создать csv-файл "rows_300.csv" со следующими столбцами:
-№-номер по порядку (от 1 до 300)
-Секунда - текущая секунда на вашем ПК
-Микросекунда - текущая миллисекунда на часах
Для наглядности на каждой итерации цикла искусственно приостанавливайте скрипт на 0,01 секунды

```python
import csv
import datetime
import time

with open('rows_300.csv', 'w', encoding = 'utf-8', newline='') as f:
    writer = csv.writer(f)
    writer.writerow(['№','Секунда', 'Микросекунда'])
    for line in range(1,301):
        writer.writerow([line,datetime.datetime.now().second, datetime.datetime.now().microsecond])
        time.sleep(0.01)
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/ab6d0c5f-0759-4c05-8376-fdcdd909a835)

![image](https://github.com/XenKov21/prob/assets/145853363/9da549a6-6844-4019-90a8-0436f063214f)


## Самостоятельная работа №7

### 1. Найдите в интернете любую стать (объем статьи не менее 200 слов), скопируйте ее содержимое в файл и напишите программу, которая считает количество слов в текстовом файле и определит самое часто встречающееся слово. Результатом выполнения задачи будет: скриншот файла со статьей, листинг кода и вывод в консоль, в котором будет указана вся необходимая информация

```python
def count_words_and_most_common(filename):
    try:
        with open(filename, 'r', encoding='utf-8') as file:
            text = file.read()
            words = text.split()
            print(f"В текстовом файле {len(words)} слов.")

            word_count = {}
            for word in words:
                if word in word_count:
                    word_count[word] += 1
                else:
                    word_count[word] = 1

            most_common_word = max(word_count, key=word_count.get)
            print(f"Самое популярное слово это: '{most_common_word}' встречается {word_count[most_common_word]} раз.")
    except FileNotFoundError:
        print("File not found.")

count_words_and_most_common('proba.txt')
```

### Результат. 
#### Статья:
![image](https://github.com/XenKov21/prob/assets/145853363/c29eddad-ee4e-43ba-bacf-bd66789a1cfe)
#### Результат:
![image](https://github.com/XenKov21/prob/assets/145853363/d6a041f2-056b-42a4-8dc5-746083b3ed25)


### 2.У вас появилась потребность в ведении книги расходов, посмотрев все существующие варианты вы пришли к выводу что вас ничего не устраивает и нужно все делать самому. Напишите программу для учета расходов. Программа должна позволять вводить информацию о расходах, сохранять ее в файл и выводить существующие данные в консоль. Ввод информации происходит через консоль. Результатом выполнения задачи будет: скриншот файла с учетом расходов, листинг кода, и вывод в консоль, с демонстрацией работоспособности программы.

```python
def enter_expense():
    date = input("Введите дату (дд-мм-гггг): ")
    item = input("Введите наименование расхода: ")
    amount = input("Введите сумму расхода: ")
    with open('expenses.txt', 'a') as file:
        file.write(f"{date} - {item} - ${amount}\n")


def show_expenses():
    with open('expenses.txt', 'r') as file:
        expenses = file.readlines()
        if not expenses:
            print("Нет сохраненных расходов.")
        else:
            print("Существующие расходы:")
            for expense in expenses:
                print(expense)

while True:
    print("Выберите действие:")
    print("1. Ввести информацию о расходе")
    print("2. Показать существующие расходы")
    print("3. Выйти")
    choice = input("Ваш выбор: ")
    if choice == '1':
        enter_expense()
    elif choice == '2':
        show_expenses()
    elif choice == '3':
        print("Программа завершена.")
        break
    else:
        print("Некорректный выбор. Попробуйте снова.")
```

### Результат. 
![image](https://github.com/XenKov21/prob/assets/145853363/40aa807d-c6eb-4fed-8847-2854413d4a5c)
#### Изменение в текстовом файле:
![image](https://github.com/XenKov21/prob/assets/145853363/e5d319b4-9a3e-40c5-8255-1db913e2516c)


### 3. . Имеется файл input.txt с текстом на латинице. Напишите программу, которая выводит следующую статистику по тексту: количество букв латинского алфавита; число слов; число строк.
Текст в файле:
Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Ожидаемый результат:
Input file contains:
108 letters
20 words
4 lines

```python
def analyze_text(filename):
    try:
        with open(filename, 'r', encoding='utf-8') as file:
            text = file.read()
            letter_count = sum(c.isalpha() for c in text)
            word_count = len(text.split())
            line_count = text.count('\n') + 1
            print(f"Input file contains:\n{letter_count} letters\n{word_count} words\n{line_count} lines")
    except FileNotFoundError:
        print("Файл не найден.")

analyze_text('input.txt')
```

### Результат.
![image](https://github.com/XenKov21/prob/assets/145853363/cfe47805-d1e6-4129-85b6-e59ed5028860)


### 4.   Напишите программу, которая получает на вход предложение, выводит его в терминал, заменяя все запрещенные слова звездочками * (количество звездочек равно количеству букв в слове). Запрещенные слова, разделенные символом пробела, хранятся  в текстовом файле input.txt. Все слова в этом файле записаны в нижнем регистре. Программа должна заменить запрещенные слова, где бы они ни встречались, даже в середине другого слова. Замена производится независимо от регистра: если файл input.txt содержит запрещенное слово exam, то слова exam, Exam, ExaM и exAm должны быть заменены на ****.
Запрещенные слова:
hello email python the exam wor is
Предложение для проверки:
Hello, world! Python IS the programming language of thE future. My EMAIL is....
PYTHON is awesome!!!!
Ожидаемый результат:
****, ***ld! ******  *** programming language of *** future. My ***** ....
****** ** awesome!!!!

```python

```

### Результат.

### 5. Поиск и замена слов в текстовом файле. Слово 'Python'  заменяется на  'Java'
```python
def find_and_replace_word(filename, target_word, replacement_word):
    try:
        with open(filename, 'r', encoding='utf-8') as file:
            text = file.read()
            modified_text = text.replace(target_word, replacement_word)
        with open(filename, 'w', encoding='utf-8') as file:
            file.write(modified_text)
        print(f"The word '{target_word}' has been replaced with '{replacement_word}' in the file.")
    except FileNotFoundError:
        print("File not found.")

find_and_replace_word('input.txt', 'Python', 'Java')
```

### Результат.  
#### До:
![image](https://github.com/XenKov21/prob/assets/145853363/8d6f4e78-7926-491d-aeff-d306e54895ce)
#### После:
![image](https://github.com/XenKov21/prob/assets/145853363/d34a1414-91a5-4920-a579-ec3ed8ffd92f)
#### Сам результат:
![image](https://github.com/XenKov21/prob/assets/145853363/29c40c11-4545-4847-a2bd-06a35d5281ce)

## Вывод.
#### Не знаю сколько раз я уже говорила спасибо, но скажу еще раз!!! К концу курса я стану джуном и меня возьмут в контур, примерно такое настроение у меня сейчас. Довольна легкая тема, но все равно приятно было читать ваше объяснение. До этого я писала в основном на java, но python становится более любим. Очень понятное объяснение и отличные задачи!
![image](https://github.com/XenKov21/prob/assets/145853363/f99232a6-8501-49ba-ae0f-88da111d25ff)

