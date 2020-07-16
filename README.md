# Содержание
- [ЛР № 12](#лабораторная-работа--12)
- [ЛР № 13](#лабораторная-работа--13)
- [ИСР № 3](#инвариативная-самостоятельная-работа--4)
    - [1 задание]
    - [2 задание]
    - [3 задание]
    - [4 задание]
- [ВСР № 3](#вариативная-самостоятельная-работа--4)
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

# [Лабораторная работа № 13](https://repl.it/@Rakleed/programming-lab13)
```python

```
![Result of lab13](https://github.com/python-basic/sem3-t4-Rakleed/blob/master/src/programming-lab13-result.png)

# Инвариативная самостоятельная работа № 4
### [4.1. ](https://repl.it/@Rakleed/programming-indepworkinvar4-1)
![Result of indepworkinvar4-1](https://github.com/python-basic/sem3-t4-Rakleed/blob/master/src/programming-indepworkinvar4-2-result.png)

### [4.2. ](https://repl.it/@Rakleed/programming-indepworkinvar4-2)
```python

```
![Result of indepworkinvar4-2](https://github.com/python-basic/sem3-t4-Rakleed/blob/master/src/programming-indepworkinvar4-2-result.png)

### [4.3. ](https://repl.it/@Rakleed/programming-indepworkinvar4-3)
```python

```
![Result of indepworkinvar4-3](https://github.com/python-basic/sem3-t4-Rakleed/blob/master/src/programming-indepworkinvar4-3-result.png)

### [4.4. ](https://repl.it/@Rakleed/programming-indepworkinvar4-4)
```python

```
![Result of indepworkinvar4-4](https://github.com/python-basic/sem3-t4-Rakleed/blob/master/src/programming-indepworkinvar4-4-result.png)

# Вариативная самостоятельная работа № 4
### [4.1. ](https://repl.it/@Rakleed/programming-indepworkvar4-1)
```python

```
![Result of indepworkvar4-1](https://github.com/python-basic/sem3-t4-Rakleed/blob/master/src/programming-indepworkvar4-1-result.png)

### [4.2. ](https://repl.it/@Rakleed/programming-indepworkvar4-2)

```python

```
![Result of indepworkvar4-2](https://github.com/python-basic/sem3-t4-Rakleed/blob/master/src/programming-indepworkvar4-2-result.png)
