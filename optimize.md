# Оптимизация, подгонка данных и численные методы решения уравнений

## Задание 1


```python
import numpy as np
from scipy.optimize import brentq

def f(x):
    return x + 1 - 1 / (x - 3)**3


print(f"f(2): {f(2)}")
print(f"f(2.9): {f(2.9)}")
print(f"f(3.1): {f(3.1)}")
print(f"f(4): {f(4)}")


interval1 = (2, 2.9)
interval2 = (3.1, 4)

try:
    root1 = brentq(f, *interval1)
    print(f"Корень на интервале {interval1}: {root1}")
except ValueError as e:
    print(f"Ошибка на интервале {interval1}: {e}")
    
try:
    root2 = brentq(f, *interval2)
    print(f"Корень на интервале {interval2}: {root2}")
except ValueError as e:
    print(f"Ошибка на интервале {interval2}: {e}")

```

    f(0.1): 0.21542514498875842
    f(1): -0.7899924966004455
    f(-1): 1.1899924966004454
    f(-0.1): 0.1845748550112416
    Ошибка на интервале (-1, -0.1): f(a) and f(b) must have different signs
    Корень на интервале (0.1, 1): 0.29285950076064027


## Задание 2

## a)


```python
import numpy as np
from scipy.optimize import brentq

def f(x):
    return 1/5 + x * np.cos(3/x)

print(f"f(0.1): {f(0.1)}")
print(f"f(1): {f(1)}")
print(f"f(-1): {f(-1)}")
print(f"f(-0.1): {f(-0.1)}")

interval1 = (-1, -0.1)
interval2 = (0.1, 1)

try:
    root1 = brentq(f, *interval1)
    print(f"Корень на интервале {interval1}: {root1}")
except ValueError as e:
    print(f"Ошибка на интервале {interval1}: {e}")
    
try:
    root2 = brentq(f, *interval2)
    print(f"Корень на интервале {interval2}: {root2}")
except ValueError as e:
    print(f"Ошибка на интервале {interval2}: {e}")
```

    f(0.1): 0.21542514498875842
    f(1): -0.7899924966004455
    f(-1): 1.1899924966004454
    f(-0.1): 0.1845748550112416
    Ошибка на интервале (-1, -0.1): f(a) and f(b) must have different signs
    Корень на интервале (0.1, 1): 0.29285950076064027


## б)


```python
import numpy as np
from scipy.optimize import newton

def f1(x):
    return 1/5 + x * np.cos(3/x)

def f1_prime(x):
    return np.cos(3/x) - 3 * np.sin(3/x) /x

initial_guesses = [-1, -0.5, 0.5, 1]

roots = []
for guess in initial_guesses:
    try:
        root = newton(f1, guess, f1_prime)
        if all(abs(root-r)> 1e-5 for r in roots):
            roots.append(root)
    except RuntimeError:
        pass
              
print ("Корни функции: ", roots)
```

    Корни функции:  []



```python

```
