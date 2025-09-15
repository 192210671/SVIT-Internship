# Assignment 4

```python
input_str = "svit"
output = (input_str + " ") * 3
output = output.strip() 
print(output)

```

    svit svit svit
    


```python
s = "hello world"

print(s.find('o'))   
print(s.index('o'))  

print(s.find('x'))   


```

    4
    4
    -1
    


```python
s = "Ram Raj Ram"
output = s.lower()
print(output) 

```

    ram raj ram
    


```python
s = "travelling"
is_palindrome = s == s[::-1]
print(is_palindrome) 

s = "svit Global solutions"
output = '-'.join(list(s))
print(output)



```

    False
    s-v-i-t- -G-l-o-b-a-l- -s-o-l-u-t-i-o-n-s
    


```python

numbers = [1, 2, 3, 4, 5]

numbers.remove(3)

numbers.insert(0, 1)

numbers.insert(2, "two-and-half")

print(numbers)

phrase = "Don't panic!"
phrase_list = list(phrase)
print(phrase_list)


```

    [1, 1, 'two-and-half', 2, 4, 5]
    ['D', 'o', 'n', "'", 't', ' ', 'p', 'a', 'n', 'i', 'c', '!']
    


```python
phrase_list = list("Don't panic!")

for char in ['p', 'a', 'n', 'D']:
    while char in phrase_list:
        phrase_list.remove(char)
phrase_list.extend(['p', 'a', 'n', 'D'])

print(phrase_list)

```

    ['o', "'", 't', ' ', 'i', 'c', '!', 'p', 'a', 'n', 'D']
    


```python
char_list = ['p', 'a', 'n', 'D', 'a']
joined_string = ''.join(char_list)
print(joined_string)


```

    panDa
    


```python
my_list = ['Hello', 100, [], 'innomatics']

my_list[2] = "Replaced Value"
print(my_list)

my_list.insert(1, "Inserted Value")
print(my_list)

```

    ['Hello', 100, 'Replaced Value', 'innomatics']
    ['Hello', 'Inserted Value', 100, 'Replaced Value', 'innomatics']
    


```python
my_tuple = (1, 2, 3, 4, 5)
reversed_tuple = my_tuple[::-1]
print(reversed_tuple)


```

    (5, 4, 3, 2, 1)
    


```python

```

