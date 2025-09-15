# Assignment 3

```python

sentence = "Earth revolves around the sun"


revolves = sentence[6:14]
print("Revolves:", revolves)


sun = sentence[-3:]
print("Sun:", sun)

```

    Revolves: revolves
    Sun: sun
    


```python

input_str = "Svit Global Solutions"

input_str_no_space = input_str.replace(" ", "")

length = len(input_str_no_space)
middle_chars = input_str_no_space[(length//2)-1 : (length//2)+1]

print("Middle two characters:", middle_chars)

```

    Middle two characters: al
    


```python
input_str = "Holiday"

first_char = input_str[0]
middle_char = input_str[len(input_str)//2]
last_char = input_str[-1]

new_str = first_char + middle_char + last_char
print("New string:", new_str)

```

    New string: Hiy
    


```python
sample_str = "   hello world   "

print("Strip:", sample_str.strip())

print("Uppercase:", sample_str.upper())

print("Find 'world':", sample_str.find("world"))

print("Replace 'world' with 'Python':", sample_str.replace("world", "Python"))

print("Split:", sample_str.strip().split())

```

    Strip: hello world
    Uppercase:    HELLO WORLD   
    Find 'world': 9
    Replace 'world' with 'Python':    hello Python   
    Split: ['hello', 'world']
    


```python

sentence = "Give papa a cup of proper coffee in a copper coffee cup"
new_sentence = sentence.replace("coffee", "tea")
print("Replaced Sentence:", new_sentence)

starts_with_hello = sentence.startswith("Hello")
ends_with_cup = sentence.endswith("cup")
print("Starts with 'Hello':", starts_with_hello)
print("Ends with 'cup':", ends_with_cup)

print("Title Case:", sentence.title())
print("Capital Case:", sentence.upper())

```

    Replaced Sentence: Give papa a cup of proper tea in a copper tea cup
    Starts with 'Hello': False
    Ends with 'cup': True
    Title Case: Give Papa A Cup Of Proper Coffee In A Copper Coffee Cup
    Capital Case: GIVE PAPA A CUP OF PROPER COFFEE IN A COPPER COFFEE CUP
    


```python

```

