# Assignment 6

# 1. Addition of Two Numbers 
Write a function add_numbers(a, b) that returns the sum of two numbers. 


```python
def add_numbers(a, b):
    return a + b
print("Answer: ",add_numbers(2,5))
```

    Answer:  7
    

# 2. Even or Odd 
Write a function is_even(num) that takes a number and returns "Even" if it’s even, 
otherwise "Odd". 



```python
def is_even(num):
    return "Even" if num % 2 == 0 else "Odd"
print("Output: ",is_even(5))
```

    Output:  Odd
    

# 3. Square of a Number 
 Write a function square(num) that returns the square of a given number. 



```python
def square(num):
    return num * num
print("Output:",square(20))
```

    Output: 400
    

# 4. Find Maximum 
Write a function find_max(a, b, c) that returns the largest of three numbers. 



```python
def find_max(a, b, c):
    return max(a, b, c)
print("Output: ",find_max(2,4,6))
```

    Output:  6
    

# 5. Factorial 
Write a function factorial(n) to calculate the factorial of a given number using 
recursion. 



```python
def factorial(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial(n - 1)
print("Output: ",factorial(10))
```

    Output:  3628800
    

# 6.Palindrome Checker 
Write a function is_palindrome(word) that checks whether a string is a palindrome. 



```python
def is_palindrome(word):
    word = word.lower()
    return word == word[::-1]
print("Output: ",is_palindrome("madam"))
```

    Output:  True
    

# 7. Fibonacci Series 
Write a function fibonacci(n) that returns the first n numbers in the Fibonacci 
sequence. 



```python

```

# 8.  Count Vowels in String 
Write a function count_vowels(text) that counts and returns the number of vowels 
in a string. 



```python
def count_vowels(text):
    vowels = "aeiouAEIOU"
    count = 0
    for char in text:
        if char in vowels:
            count += 1
    return count
print("Output: ",count_vowels("Eswar"))
```

    Output:  2
    

# 9.Prime Number Check 
Write a function is_prime(n) that checks whether a given number is prime. 



```python
def is_prime(n):
    if n <= 1:
        return False
    for i in range(2, n):
        if n % i == 0:
            return False
    return True
print("Output: ",is_prime(2))
```

    Output:  True
    

# 10.  List Sum without Built-in sum() 
Write a function list_sum(numbers) that returns the sum of all elements in a list 
without using the built-in sum() function.


```python
def list_sum(numbers):
    total = 0
    for num in numbers:
        total += num
    return total
print("Output: ",list_sum([1, 2, 3, 4, 5])) 
```

    Output:  15
    


```python

```
