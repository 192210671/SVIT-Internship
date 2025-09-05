```python
# Question 1
a=12
b=5
print(a+b)
print(a-b)
print(a*b)
print(a/b)
print(a%b)
```

    17
    7
    60
    2.4
    2
    


```python
# Question 2
exp=(8+2)*(3-1)**2/2 
print(exp)
```

    20.0
    


```python
# Question 3
p=True
q=False
r=True

print(p and q)
print(p or q)
print( not r)

```

    False
    True
    False
    


```python

# Question 4
exp2=10+2*3/4-5**2
# PEMDAS
# 5**2 = 25
# 2*3  =6
# 2*3/4 =6/4 => 1.5
# 10+1.5 = 11.5
# 11.5-25 => -13.5
print(exp2)
```

    -13.5
    


```python

# Question 5
x = True
y = False

print(x and y)  
print(x or y)   
print(not x)    


op1 = 6  # 110
op2 = 3  # 011 

print(op1 & op2)   
print(op1 | op2)  
print(~op1) 
```

    False
    True
    False
    2
    7
    -7
    


```python

# Question 6
v1=1
v2=12.5
v3="String"
v4=True
# etc...
print(type(v1))
print(type(v2))
print(type(v3))
print(type(v4))
```

    <class 'int'>
    <class 'float'>
    <class 'str'>
    <class 'bool'>
    


```python

# Question 7
width=17
height=12.0
delimiter='.'

print(width , type(width))
print(height, type(height))
print(delimiter, type(delimiter))
```

    17 <class 'int'>
    12.0 <class 'float'>
    . <class 'str'>
    


```python
# Question 8

d1=10
d2='10'
d3=True
d4=10.5
print(type(d1))
print(type(d2))
print(type(d3))
print(type(d4))
```

    <class 'int'>
    <class 'str'>
    <class 'bool'>
    <class 'float'>
    


```python

# Question 9
# 4/3 pi r**3
import math as m
radius=5
volume=(4/3)*(m.pi)*(radius**3)
print(volume)
```

    523.5987755982989
    


```python

```

