# Assignment 5

```python
my_list = [1, 2, 2, 3, 4, 4, 5]
unique_list = list(set(my_list))
print(unique_list)


```

    [1, 2, 3, 4, 5]
    


```python
list1 = [1, 2, 3, 4]
list2 = [3, 4, 5, 6]

common_elements = list(set(list1) & set(list2))
print(common_elements)


```

    [3, 4]
    


```python
def count_unique_words(text):
    words = text.split()
    unique_words = set(words)
    return len(unique_words)

input_text = "hello world hello"
print(count_unique_words(input_text))


```

    2
    


```python
set_a = {1, 2, 3, 4}
set_b = {3, 4, 5, 6}

print("Union:", set_a | set_b)         
print("Intersection:", set_a & set_b) 
print("Difference (a - b):", set_a - set_b) 
print("Symmetric Difference:", set_a ^ set_b) 

```

    Union: {1, 2, 3, 4, 5, 6}
    Intersection: {3, 4}
    Difference (a - b): {1, 2}
    Symmetric Difference: {1, 2, 5, 6}
    


```python
dict1 = {'a': 100, 'b': 200, 'c': 300}
dict2 = {'a': 300, 'b': 200, 'd': 400}

merged_dict = dict1.copy()

for key, value in dict2.items():
    if key in merged_dict:
        merged_dict[key] += value
    else:
        merged_dict[key] = value

print(merged_dict)


```

    {'a': 400, 'b': 400, 'c': 300, 'd': 400}
    


```python
input_dict = {"a": 5, "b": 9, "c": 3}
max_key = max(input_dict, key=input_dict.get)
print(max_key)


```

    b
    


```python
my_dict = {"a": 5, "b": 10, "c": 3}
total_sum = sum(my_dict.values())
print(total_sum)


```

    18
    


```python
dict1 = {'a': 1, 'b': 2, 'c': 3}
dict2 = {'b': 4, 'c': 5, 'd': 6}

common_keys = set(dict1.keys()) & set(dict2.keys())
print(common_keys)


```

    {'c', 'b'}
    


```python
my_dict = {'a': 1, 'b': 2, 'c': 1, 'd': 3}

unique_values = set(my_dict.values())
print(unique_values)


```

    {1, 2, 3}
    


```python
s = {"a", "x"}
d = {"a": 1, "b": 2}

missing_keys = s - set(d.keys())
print(missing_keys)


```

    {'x'}
    


```python

```

