# Эмпирический анализ временной сложности алгоритмов
Иванова Полина
ИУ10-38
## Задания
### Задание 1.1


```python
import random, usage_time
import matplotlib.pyplot as plt

def sum_elements(v: list):
    return sum(v)


items = range(1, 10**5 * 14, 50000)

func = usage_time.get_usage_time()(sum_elements)

times = [
    func([random.randint(1, 3) for _ in range(n)]) 
    for n in items
]


plt.plot(items, times, 'm-o', linewidth=1.5, markersize=5)
ax = plt.gca()

plt.title('time of sum')
ax.set_xlabel('number of elements')
ax.set_ylabel('seconds')
plt.grid(True, linestyle='--', alpha=0.5)
plt.show()
```
![Uploading Screenshot 2025-09-28 203300.png…]()



### Задание 1.3


```python
import random, usage_time
import matplotlib.pyplot as plt


def multiplication_nums(v: list):
    mult = 1
    for num in v:
        mult *= num
    return mult


items = range(1, 10**5 * (20 - 7), 50000)
func = usage_time.get_usage_time()(multiplication_nums)
times = [
    func([
        random.randint(1, 3) 
        for _ in range(n)
    ]) 
    for n in items
]

fig = plt.plot(items, times, 'bo-')
ax = plt.gca()

plt.title('The execution time of the get multiplication of list numbers algorithm')
ax.set_xlabel('Number of elements')
ax.set_ylabel('Time, sec')
```
![png](Lab_01_files/Lab_01_3_1.png)
    


### Задание 1.5


```python
import random, usage_time
import matplotlib.pyplot as plt


def get_max(v: list):
    max_num = 0
    for num in v:
        if num > max_num:
            max_num = num
    return max_num


items = range(1, 10**5 * (20 - 7), 50000)
func = usage_time.get_usage_time()(get_max)
times = [
    sum([
        func([
            random.randint(1, 10) 
            for _ in range(n)
        ])
        for _ in range(20)
    ]) / 20
    for n in items
]

fig = plt.plot(items, times, 'bo-')
ax = plt.gca()

plt.title('The execution time of the getting max of list numbers algorithm')
ax.set_xlabel('Number of elements')
ax.set_ylabel('Time, sec')
```
![png](Lab_01_files/Lab_01_5_1.png)
    


### Задание 1.8


```python
import random, usage_time
import matplotlib.pyplot as plt


def harmonic_mean(v: list):
    summ = 0
    for num in v:
        summ += 1 / num
    mean = len(v) / summ
    return mean


items = range(1, 10**5 * (20 - 7), 50000)
func = usage_time.get_usage_time()(harmonic_mean)
times = [
    sum([
        func([
            random.randint(1, 10) 
            for _ in range(n)
        ])
        for _ in range(20)
    ]) / 20
    for n in items
]

fig = plt.plot(items, times, 'bo-')
ax = plt.gca()

plt.title('The execution time of the get harmonic mean of list numbers algorithm')
ax.set_xlabel('Number of elements')
ax.set_ylabel('Time, sec')
```
![png](Lab_01_files/Lab_01_7_1.png)
    


### Задание 2


```python
import random, usage_time
import matplotlib.pyplot as plt


def matrix_mult(matrix_a: list, matrix_b: list):
    matrix_c = [
        [0 for _ in range(len(matrix_a))]
        for _ in range(len(matrix_a))
    ]

    for y in range(len(matrix_a)):
        for x in range(len(matrix_a)):
            num = 0
            for i in range(len(matrix_a)):
                num += matrix_a[y][i] * matrix_b[i][x]
            matrix_c[y][x] = num
    print(len(matrix_a))
    return matrix_c


items = range(1, 10**2 * (20 - 7), 100)
func = usage_time.get_usage_time()(matrix_mult)
times = [
    func(
        [
            [
                random.randint(1, 3)
                for _ in range(n)
            ]
            for _ in range(n)
        ],
        [
            [
                random.randint(4, 6)
                for _ in range(n)
            ]
            for _ in range(n)
        ]
    )
    for n in items
]

fig = plt.plot(items, times, 'bo-')
ax = plt.gca()

plt.title('The execution time of the get matrix multiplication of list numbers algorithm')
ax.set_xlabel('Number of elements')
ax.set_ylabel('Time, sec')
```
![png](Lab_01_files/Lab_01_9_2.png)
    

