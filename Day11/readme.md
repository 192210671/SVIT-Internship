# Day 11

```python
a=10
b=20
a,b=b,a
print(a,b)
```

    20 10
    

# Looping Statements
- While Loop
- For Loop

**While Loop**: it  will check the condition is true
= 1



```python
var=1
while var<=30:
    print("count is :",var)
    var+=1
```

    count is : 1
    count is : 2
    count is : 3
    count is : 4
    count is : 5
    count is : 6
    count is : 7
    count is : 8
    count is : 9
    count is : 10
    count is : 11
    count is : 12
    count is : 13
    count is : 14
    count is : 15
    count is : 16
    count is : 17
    count is : 18
    count is : 19
    count is : 20
    count is : 21
    count is : 22
    count is : 23
    count is : 24
    count is : 25
    count is : 26
    count is : 27
    count is : 28
    count is : 29
    count is : 30
    


```python
var1=1
while var1<=15:
    if var1%2!=0:
        print(var1)
    var1+=1

```

    1
    3
    5
    7
    9
    11
    13
    15
    


```python
var1=1
while var1<=15:
    if var1%2==0:
        print(var1)
    var1+=1

```

    2
    4
    6
    8
    10
    12
    14
    


```python
# money=100, -20
money=100
while money>0:
    money-=20

if money==0:
    print("Empty")
else:
    print("you have some money",money)

```

    Empty
    


```python
password = "eswar"

while True:
    check = input("Enter the Password: ")
    if check == password:
        print("Login Successfully")
        break
    else:
        print("Please Try Again")

```

    Enter the Password:  eswa
    

    Please Try Again
    

    Enter the Password:  eswar
    

    Login Successfully
    


```python
#mobile charge=0
#mobile charge=100

initial=0
while initial!=100:
    print("charge: ",initial)
    initial+=1
    if initial==100:
        print("Battery fully charged")
        break
        
```

    charge:  0
    charge:  1
    charge:  2
    charge:  3
    charge:  4
    charge:  5
    charge:  6
    charge:  7
    charge:  8
    charge:  9
    charge:  10
    charge:  11
    charge:  12
    charge:  13
    charge:  14
    charge:  15
    charge:  16
    charge:  17
    charge:  18
    charge:  19
    charge:  20
    charge:  21
    charge:  22
    charge:  23
    charge:  24
    charge:  25
    charge:  26
    charge:  27
    charge:  28
    charge:  29
    charge:  30
    charge:  31
    charge:  32
    charge:  33
    charge:  34
    charge:  35
    charge:  36
    charge:  37
    charge:  38
    charge:  39
    charge:  40
    charge:  41
    charge:  42
    charge:  43
    charge:  44
    charge:  45
    charge:  46
    charge:  47
    charge:  48
    charge:  49
    charge:  50
    charge:  51
    charge:  52
    charge:  53
    charge:  54
    charge:  55
    charge:  56
    charge:  57
    charge:  58
    charge:  59
    charge:  60
    charge:  61
    charge:  62
    charge:  63
    charge:  64
    charge:  65
    charge:  66
    charge:  67
    charge:  68
    charge:  69
    charge:  70
    charge:  71
    charge:  72
    charge:  73
    charge:  74
    charge:  75
    charge:  76
    charge:  77
    charge:  78
    charge:  79
    charge:  80
    charge:  81
    charge:  82
    charge:  83
    charge:  84
    charge:  85
    charge:  86
    charge:  87
    charge:  88
    charge:  89
    charge:  90
    charge:  91
    charge:  92
    charge:  93
    charge:  94
    charge:  95
    charge:  96
    charge:  97
    charge:  98
    charge:  99
    Battery fully charged
    


```python
# continue = skipping the iteration
var1=0
while var1<10:
    var1+=1
    if var1==5:
        print("value skipped")
        continue
    print(var1)    

```

    1
    2
    3
    4
    value skipped
    6
    7
    8
    9
    10
    


```python
num=int(input("Enter the Number: "))
temp=num
def getDigits(temp):
    count=0
    while temp>0:
       
        count+=1
        temp=temp//10
        
        
    return count    
count=getDigits(temp)
sum=0
while temp>0:
    r=temp%10
    sum+=r**count
    temp=temp//10

if sum==num:
    print("Armstrong Number")
else:
    print("Not Armstrong Number")
    
```

    Enter the Number:  153
    

    Armstrong Number
    


```python

```

