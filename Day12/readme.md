# Day12
```python
word="icecreammm"
count=0
vowels="aeiouAEIOU"
for ch in word:
    if ch not in vowels:
        count+=1
print("No of Consonants: ",count)        
```

    No of Vowels:  6
    


```python
n=int(input("Enter the Number: "))
sum=0
for i in range(1,n+1):
    sum+=i
print("Sum of Natural Numbers: ",sum)    
```

    Enter the Number:  10
    

    Sum of Natural Numbers:  55
    


```python
n=int(input("Enter the Number: "))
m=int(input("Enter the limit ,like 10,20....."))
for i in range(1,m+1):
    print(n,"*",i,"=",n*i)
```

    Enter the Number:  2
    Enter the limit ,like 10,20..... 10
    

    2 * 1 = 2
    2 * 2 = 4
    2 * 3 = 6
    2 * 4 = 8
    2 * 5 = 10
    2 * 6 = 12
    2 * 7 = 14
    2 * 8 = 16
    2 * 9 = 18
    2 * 10 = 20
    


```python
for i in range(1,3):
    for j in range(1,4):
        print(i,j, end=" ")
        
```

    1 1 1 2 1 3 2 1 2 2 2 3 


```python
for i  in range(1,6):
    for j in range(i):
        print("*",end=" ")
    print()    
```

    * 
    * * 
    * * * 
    * * * * 
    * * * * * 
    


```python
names=["eswar","revanth","hemanth"]
for name in names:
    print("Attendance Marked for : ",name)
    if name.lower()=="revanth":
        print("Attendance closed")
        break
```

    Attendance Marked for :  eswar
    Attendance Marked for :  revanth
    Attendance closed
    


```python
def mark_attendace(name):
    check=["present","absent"]
    n=int(input("Mark Attendance 0-for present, 1- for absent: "))
    print("


```


```python
def making(order):
    print("1. Take some water.")
    print("2. Pour the water into a bowl.")
    print("3. Put the bowl on the stove.")
    print("4. Add milk .")
    print(f"5. Add '{order}' powder as per the order.")
    print("6. Wait for 15 minutes.")
    print("\nYour order is ready! Enjoy ")


order = input("Please enter the beverage order : ")
making(order)

```

    Please enter the beverage order (e.g., tea, coffee, hot chocolate):  coffee
    

    1. Take a glass of water.
    2. Pour the water into a bowl.
    3. Put the bowl on the stove.
    4. Add milk to the mixture.
    5. Add 'coffee' powder as per the order.
    6. Wait for 15 minutes.
    
    Your order is ready! Enjoy 
    


```python
n=int(input("Enter the Number: "))
fact=1
for i in range(1,n+1):
    fact*=i
print("Factorial of ",n,"is ",fact )    
```

    Enter the Number:  5
    

    Factorial of  5 is  120
    


```python

```
