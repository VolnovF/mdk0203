# Интегрирование

## Задание 1


```python
import numpy as np;
from scipy.integrate import quad

def integrand(x):
    return np.floor(x) -2* np.floor(x/2)

result, error = quad(integrand, 0, 6)

print("Результат интеграла: ", result)
print("Погрешность: ", error)
```

    Результат интеграла:  2.999964948683555
    Погрешность:  0.0009520766614602031


    <ipython-input-2-ef31fd969dde>:7: IntegrationWarning: The maximum number of subdivisions (50) has been achieved.
      If increasing the limit yields no improvement it is advised to analyze 
      the integrand in order to determine the difficulties.  If the position of a 
      local difficulty can be determined (singularity, discontinuity) one will 
      probably gain from splitting up the interval and calling the integrator 
      on the subranges.  Perhaps a special-purpose integrator should be used.
      result, error = quad(integrand, 0, 6)


# Задание 2

## a)



```python
from scipy.integrate import quad

def integrand_a(x):
    return (x**4 * (1-x)**4) / (1+x**2)

result_a, error_a = quad(integrand_a, 0, 1)
print("Результат интеграла(a): ", result_a)
print("Погрешность: ", error_a)
```

    Результат интеграла(a):  0.0012644892673496185
    Погрешность:  1.1126990906558069e-14


## б)



```python
import numpy as np;

def integrand_b(x):
    return x**3/ (np.exp(x)-1)

result_b, error_b = quad(integrand_b, 0, np.inf)
print("Результат интеграла(б): ", result_b)
print("Погрешность: ", error_b)
```

    Результат интеграла(б):  6.49393940226683
    Погрешность:  2.62847130244751e-09


    <ipython-input-7-8c1def05e05f>:4: RuntimeWarning: overflow encountered in exp
      return x**3/ (np.exp(x)-1)


## в)


```python
import numpy as np;
from scipy.integrate import quad

def integrand_v(x):
    return x**(-x)

result_v, error_v = quad(integrand_v, 0, 1)
print("Результат интеграла(в): ", result_v)
print("Погрешность: ", error_v)
```

    Результат интеграла(в):  1.2912859970626636
    Погрешность:  3.668487735808412e-11


## г)


```python
p = 2
def integrand_g(x):
    return (np.log(1/x))**p

result_g, error_g = quad(integrand_g, 0, 1)
print("Результат интеграла(г): ", result_g)
print("Погрешность: ", error_g)
```

    Результат интеграла(г):  2.0000000000000018
    Погрешность:  1.687538997430238e-14


## д)


```python
z = 1
def integrand_d(theta):
    return np.exp(z*np.cos(theta))

result_d, error_d = quad(integrand_d, 0, 2*np.pi)
print("Результат интеграла(д): ", result_d)
print("Погрешность: ", error_d)
```

    Результат интеграла(д):  7.954926521012844
    Погрешность:  2.436596551939076e-11



```python

```
