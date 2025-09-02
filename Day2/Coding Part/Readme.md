```python
fruits=["apples","guva","banana"]
```


```python
print(fruits)
```

    ['apples', 'guva', 'banana']
    


```python
check=[1,"a"]
```


```python
print(check)
```

    [1, 'a']
    


```python
name=first_name="yashwanth"
```


```python
print(name)
print(first_name)
```

    yashwanth
    yashwanth
    

## Data Types
* Numeric Type
* Sequence Type
* Mapping Type
* Boolean Type


```python
a=10
print(type(a))
b=1.03
print(type(b))
c=1.00000000000000000000000000000001
print(type(c))
```

    <class 'int'>
    <class 'float'>
    <class 'float'>
    

# Python Data Types

Python's built-in data types can be categorized as follows:

## Numeric Types
- **int**: Integer numbers, positive or negative, without decimals. Example: `5`, `-3`
- **float**: Floating-point numbers (decimals). Example: `3.14`, `-2.5`
- **complex**: Complex numbers with real and imaginary parts. Example: `2 + 3j`

## Sequence Types
- **str**: String, a sequence of Unicode characters. Example: `"hello"`
- **list**: Ordered, mutable collection of items. Example: `[1, 2, 3]`
- **tuple**: Ordered, immutable collection of items. Example: `(1, 2, 3)`

## Mapping Type
- **dict**: Unordered collection of key-value pairs. Example: `{"name": "Alice", "age": 25}`

## Set Types
- **set**: Unordered collection of unique items, mutable. Example: `{1, 2, 3}`
- **frozenset**: Unordered collection of unique items, immutable.

## Boolean Type
- **bool**: Represents truth values. Can be `True` or `False`.

## Binary Types
- **bytes**: Immutable sequence of bytes. Example: `b'hello'`
- **bytearray**: Mutable sequence of bytes.
- **memoryview**: Memory view object for byte data.

---

Variables in Python are instances of these classes, and their type can be checked with `type()` function.




```python
# Complex 
complex=2+3j
print(type(complex))
```

    <class 'complex'>
    


```python
str_1="SVIT"
print(str_1)
print(type(str_1))
```

    SVIT
    <class 'str'>
    

# Setting Specific Data types



```python
s=str("Hello")
print(s)
```

    Hello
    


```python
SVIT_TEAM=["Eswar","Revanth","Kalyan"]
print(SVIT_TEAM)
my_names=list(["Eswar","Revanth"])
print(my_names)

```

    ['Eswar', 'Revanth', 'Kalyan']
    ['Eswar', 'Revanth']
    


```python

```
