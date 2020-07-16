# Содержание
- [ЛР № 12](#лабораторная-работа--12)
- [ИСР № 4](#инвариативная-самостоятельная-работа--4)
    - [1 задание](#41-реализация-программы-для-считывания-данных-из-файла-json-и-их-вывод-в-табличном-формате-и-тестирование-работоспособности)
    - [2 задание](#42-дополнить-программу-задания-41-тестами-с-использованием-библиотеки-doctest)
    - [3 задание]
- [ВСР № 4](#вариативная-самостоятельная-работа--4)
    - [1 задание]
    - [2 задание]

# [Лабораторная работа № 12](https://repl.it/@Rakleed/programming-lab12)
```python
"""
    Автор: Моисеенко Павел, группа № 1, подгруппа № 2.

    ЛР 12. Задание: написать программу для вычисления факториала.

"""


def main():
    number = -1
    input_number = input("Введите число: ")
    try:
        number = int(input_number)
    except:
        print("Вы ввели неверное значение.")
    result = factorial(number)
    print("Факториал {} = {}.".format(input_number, result))


def factorial(number):
    if type(number) is int and number >= 0:
        fl = 1
        i = number
        if number == 0:
            return 1
        else:
            while i > 1:
                fl = fl * i
                i -= 1
        return fl
    else:
        raise ValueError("Вы ввели неверное число.")


main()
```
![Result of lab12](https://github.com/python-basic/sem3-t4-Rakleed/blob/master/src/programming-lab12-result.png)

# Инвариативная самостоятельная работа № 4
### [4.1. Реализация программы для считывания данных из файла JSON и их вывод в табличном формате, и тестирование работоспособности.](https://repl.it/@Rakleed/programming-indepworkinvar4-1)
```python
"""
    Автор: Моисеенко Павел, группа № 1, подгруппа № 2.

    ИСР 4.1. Задание: разработать программу для считывания данных JSON-
    формата из файла и вывод их в табличном виде на экран. Организо-
    вать тестирование работоспособности программы с помощью assert,
    print.

"""

import json


def json_table(data):
    table = []
    string = '| {id:^3} | {first_name:^10} | {last_name:^15} | {email:^30} | {gender:^6} | {ip_address:^16} |'
    t_caption = '| {:^3} | {:^10} | {:^15} | {:^30} | {:^6} | {:^16} |'.format('id', 'first_name', 'last_name', 'email',
                                                                               'gender', 'ip_address')
    header = '-' * len(t_caption)

    table.append(header)
    table.append(t_caption)
    table.append(header)

    for element in range(len(data)):
        temp = data[element]
        res = string.format(**temp)
        table.append(res)
    table.append(header)
    return table


def test_function(function, arg):
    try:
        assert function(arg)[1
               ] == '| id  | first_name |    last_name    |             email              | gender |    ip_address    |'
    except:
        print('Тест провален, шапка не соответствует ожиданиям.')
    try:
        assert type(function(arg)) is tuple
    except:
        print('Тест на тип провален.', type(function(arg)))
    try:
        assert len(function(arg)) == 100
    except:
        print('Количество строк не соответствует ожиданиям —',
              len(function(arg)))


def main():
    with open('file.json') as f:
        data_dict = json.load(f)

    test_function(json_table, data_dict)


main()
```
![Result of indepworkinvar4-1](https://github.com/python-basic/sem3-t4-Rakleed/blob/master/src/programming-indepworkinvar4-1-result.png)

### [4.2. Дополнить программу задания 4.1 тестами с использованием библиотеки doctest.](https://repl.it/@Rakleed/programming-indepworkinvar4-2)
```python
"""
    Автор: Моисеенко Павел, группа № 1, подгруппа № 2.

    ИСР 4.2. Задание: дополнить программу задания 4.1 тестами с
    использованием библиотеки doctest.

"""

import json


def json_table():
    """
    >>> json_table()[1]
    '| id  | first_name |    last_name    |             email             | gender |    ip_address    |'
    """

    with open('file.json') as f:
        data_dict = json.load(f)
    table = []
    string = '| {id:^3} | {first_name:^10} | {last_name:^15} | {email:^30} | {gender:^6} | {ip_address:^16} |'
    t_caption = '| {:^3} | {:^10} | {:^15} | {:^30} | {:^6} | {:^16} |'.format('id', 'first_name', 'last_name', 'email',
                                                                               'gender', 'ip_address')
    header = '-' * len(t_caption)
    table.append(header)
    table.append(t_caption)
    table.append(header)
    for element in range(len(data_dict)):
        temp = data_dict[element]
        res = string.format(**temp)
        table.append(res)
    table.append(header)
    return table


def main():
    foo = json_table()


if __name__ == "__main__":
    import doctest
    doctest.testmod()
```
![Result of indepworkinvar4-2](https://github.com/python-basic/sem3-t4-Rakleed/blob/master/src/programming-indepworkinvar4-2-result.png)

### [4.3. Дополнить программу задания 4.1, 4.2 тестами с использованием пакета py.test.](https://repl.it/@Rakleed/programming-indepworkinvar4-3)
```python
"""
    Автор: Моисеенко Павел, группа № 1, подгруппа № 2.

    ИСР 4.3. Задание: дополнить программу задания 4.1, 4.2 тестами с
    использованием пакета py.test.

"""

import pytest
import json


def json_table(data):
    table = []
    string = '| {id:^3} | {first_name:^10} | {last_name:^15} | {email:^30} | {gender:^6} | {ip_address:^16} |'
    t_caption = '| {:^3} | {:^10} | {:^15} | {:^30} | {:^6} | {:^16} |'.format('id', 'first_name', 'last_name', 'email',
                                                                               'gender', 'ip_address')
    header = '-' * len(t_caption)

    table.append(header)
    table.append(t_caption)
    table.append(header)

    for element in range(len(data)):
        temp = data[element]
        res = string.format(**temp)
        table.append(res)
    table.append(header)

    return table


def main():
    with open('file.json') as f:
        data_dict = json.load(f)
    foo = json_table(data_dict)


def test_json_table():
    assert json_table([{"id": 1, "first_name": "Susann", "last_name": "Wyldish", "email": "swyldish0@bing.com",
                        "gender": "Female", "ip_address": "112.109.35.15"},
                       {"id": 2, "first_name": "Oliy", "last_name": "Bruton", "email": "obruton1@forbes.com",
                        "gender": "Female", "ip_address": "166.20.188.54"},
                       {"id": 3, "first_name": "Ginelle", "last_name": "Inkpen", "email": "ginkpen2@tinypic.com",
                        "gender": "Female", "ip_address": "208.129.167.239"}]) == [
               '---------------------------------------------------------------------------------------------------',
               '| id  | first_name |    last_name    |             email              | gender |    ip_address    |',
               '---------------------------------------------------------------------------------------------------',
               '|  1  |   Susann   |     Wyldish     |       swyldish0@bing.com       | Female |  112.109.35.15   |',
               '|  2  |    Oliy    |     Bruton      |      obruton1@forbes.com       | Female |  166.20.188.54   |',
               '|  3  |  Ginelle   |     Inkpen      |      ginkpen2@tinypic.com      | Female | 208.129.167.239  |',
               '---------------------------------------------------------------------------------------------------']


if __name__ == "__main__":
    main()
```
![Result of indepworkinvar4-3](https://github.com/python-basic/sem3-t4-Rakleed/blob/master/src/programming-indepworkinvar4-3-result.png)

# Вариативная самостоятельная работа № 4
### [4.1. ](https://repl.it/@Rakleed/programming-indepworkvar4-1)
```python

```
![Result of indepworkvar4-1](https://github.com/python-basic/sem3-t4-Rakleed/blob/master/src/programming-indepworkvar4-1-result.png)

### [4.2. ](https://repl.it/@Rakleed/programming-indepworkvar4-2)

```python

```
![Result of indepworkvar4-2](https://github.com/python-basic/sem3-t4-Rakleed/blob/master/src/programming-indepworkvar4-2-result.png)
