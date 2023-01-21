# Week 5

1/1/2023

16:00-17:00

## Review

<img src="http://www.math.snu.ac.kr/~ernestryu/img/ryu_photo.jpg" width=200/>

Reference: [Ernest K. Ryu](http://www.math.snu.ac.kr/~ernestryu/courses/deep_learning.html)

### Variable types
Python will infer the type when you define the variable. With `x = 2`, `x` is set to an **int**. With `x = 2.0`, `x` is set to a **float**.<br>
`type(...)` displays a variable's type (useful for understanding the details of the code when debugging).

- **int** <br>
A (signed) integer ...−2,−1,0,1,2,...


```python
x = 2
print(type(x))
```

- **float** <br>
A real number with 16 digits of precision. (Equivalent to "double" in other languages. Python does not natively support single-precision floating point numbers.)


```python
y = 2.0
print(type(y))
```

- **str** <br>
A string, a sequence of 0 or more characters. Enclosed within a pair of single quotes `'` or a pair of double quotes `"`.


```python
a = "Hello World!"
print(type(a))
print(a)
```

__Exercise__ : Read 3.1.2 in the [Python tutorial](https://docs.python.org/3.7/tutorial/introduction.html) and check the output of the following. (Double click the cell to see the actual code.)
-  print("McDonald's")
-  print("McDonald\'s")
-  print('McDonald\'s')
-  print('McDonald's')
-  print(r"McDonald\'s")
-  print(3*"McDonald\'s")
-  print("McDonald" + "\'s")
-  print("McDonald" "\'s")
-  print("""McDonald
              \'s""")


```python
print("""McDonald
    multiline string
              \'s""")
```

Indices refer to positions **between** characters. The left edge of the first character numbered **0**. Then the right edge of the last character of a string of length **n** characters has index **n**. 

<pre>
 +---+---+---+---+---+---+
 | P | y | t | h | o | n |
 +---+---+---+---+---+---+
 0   1   2   3   4   5   6
-6  -5  -4  -3  -2  -1
</pre>

Python also uses negative indexes.


To access a single element of `seq` immediately after index `ind`, use `seq[ind]`.

__Exercise__: If `s = "abcdefg"`, what are the outputs to the following code?
-  print(s[0])
-  print(s[6])
-  print(s[7])


```python
s = "Python"
print(s[:])
```


```python
s = "고현수"
s[0:2]
```




    '고현'



The slice notation specifies two index positions separated by a colon (`:`) to access subsequences.<br>
`seq[start:stop]` returns elements in `seq` between `start` and `stop`. If `start` or `stop` are omitted, they are set to the beginning or the end. If `stop` is larger than the end of the string, `stop` is set to the end of the string.

__Exercise__: If `s = "abcdefg"`, what are the outputs to the following code?
-  print(s[0])
-  print(s[6])
-  print(s[7])
-  print(s[-1])
-  print(s[1:3])
-  print(s[:3])
-  print(s[3:])
-  print(s[:])
-  print(s[0:-2])
-  print(s[0:100])
-  s[0] = 'z'
-  s[0:3] = ['x','y','z']
-  print(len(s))


```python
s[0] = 'z'
```

`seq[start:stop:step]` returns elements in `seq` between `start` and `stop` separated by `step`. (`step` is `1` by default.)


```python
s = 'Python'
print(s[::2])  # print elements in even-numbered positions
print(s[1::2])  # print elements in odd-numbered positions
print(s[::-1])  # print elements in reverse order
print(s[:-4:-1])
```

### The range function: 
Generates sequences of numbers in the form of a list. The provided end point is not included. (Actually, `range` creates an iterable object, not a list. More on this later.)


```python
print(list(range(10)))  # 0, 1, ..., 9
print(list(range(1,10)))  # 1, 2, ..., 9 
print(list(range(21,-1,-2)))  # 21, 19, 17, ..., 1
```

    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    [1, 2, 3, 4, 5, 6, 7, 8, 9]
    [21, 19, 17, 15, 13, 11, 9, 7, 5, 3, 1]
    

### If-else statement

You can write if-else statements with<br>
`if <condition>:`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`code in if`<br>
`elif <condition>:`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`code in else-if`<br>
`elif <condition>:`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`code in else-if`<br>
`else :`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`code in else`<br>
`code after if-else`

The indentation for the if-else blocks is not optional.


```python
x = -10
if x > 0:
    print("x is positive")
elif x < 0:
    print("x is negative")
else:
    print("x is 0")

print("Code after if-else statement")
```

    x is negative
    Code after if-else statement
    


```python
def print_num(x):
    if x > 0:
        print("x is positive")
    elif x < 0:
        print("x is negative")
    else:
        print("x is 0")

print_num(0)
print_num(10)
print_num(-10)
```

    x is 0
    x is positive
    x is negative
    

## Lists
A **list** is an ordered sequence of 0 or more comma-delimited elements enclosed within square brackets (`[`, `]`). 


```python
s = [1,2,3,4,5,6,7,8]
print(s[2:5])
```

    [3, 4, 5]
    

Use `+` to concatenate lists.


```python
s = ['a','b','c','d','e']+['f','g']
print(s)
```

    ['a', 'b', 'c', 'd', 'e', 'f', 'g']
    

__Exercise:__ If `s = ['a','b','c','d','e'] + ['f','g']`, what are the outputs to the following code?
-  print(s[0])
-  print(s[6])
-  print(s[7])
-  print(s[-1])
-  print(s[1:3])
-  print(s[:3])
-  print(s[3:])
-  print(s[0:-2])
-  print(s[0:100])
-  s[0] = 'z'; print(s)
-  s[0:3] = ['x','y','z']; print(s)


```python
s[0:3] = ['x','y','z']
print(s)
```

Lists may also have lists as their elements:


```python
K=[[1,2],[3,4,5],'s']
print(K[0][1])
print(K[0][:])
print(K[1])
print(K[2])
```

## The split function


```python
"1-2-3-4-5".split("-")
```




    ['1', '2', '3', '4', '5']




```python
"1-2-3--4-5".split("-")
```




    ['1', '2', '3', '', '4', '5']




```python
"1 2 3 4 5".split(" ")
```




    ['1', '2', '3', '4', '5']




```python
"1 2 3  4 5".split(" ")
```




    ['1', '2', '3', '', '4', '5']




```python
"1 2 3 4 5".split()  # default
```




    ['1', '2', '3', '4', '5']



## The map function
List의 각 요소에 동일한 함수를 적용한다.


```python
people = ["현수", "하람", "종원", "서빈"]
def name_dec(name):
    return name + "??!"
# ['현수??!', '하람??!', ...]
list(map(name_dec, people))
```




    ['현수??!', '하람??!', '종원??!', '서빈??!']




```python
temp = input()
print(type(temp))
```

    1 2
    <class 'str'>
    


```python
temp = input().split()
print(type(temp))
print(temp)
```

    1 2 3
    <class 'list'>
    ['1', '2', '3']
    


```python
a, b, c = map(int, input().split())
print(a)
print(b)
```

    1 2 345
    1
    2
    

### 1008: A/B
두 정수 A와 B를 입력받은 다음, A/B를 출력하는 프로그램을 작성하시오.


```python
a, b = map(int, input().split())
print(a/b)
```

    1 3
    0.3333333333333333
    

### 2480: 주사위 세 개


```python
print(10 > 3 | 10 < 3)
```

    False
    


```python
a, b, c = map(int, input().split())
if a == b and b == c:
    print(10000 + a * 1000)
elif a == b or a == c:
    print(1000 + a * 100)
elif b == c:
    print(1000 + b * 100)
elif a > b and a > c:
    print(a * 100)
elif b > c and b > a:
    print(b * 100)
else:
    print(c * 100)
```

    3 3 6
    1300
    


```python
max(1, 3, 5)
```




    5




```python
a, b, c = map(int, input().split())
if a == b and b == c:
    print(10000 + a * 1000)
elif a == b or a == c:
    print(1000 + a * 100)
elif b == c:
    print(1000 + b * 100)
else:
    print(100 * max(a, b, c))
```

### 1110: 더하기 사이클
0보다 크거나 같고, 99보다 작거나 같은 정수가 주어질 때 다음과 같은 연산을 할 수 있다. 먼저 주어진 수가 10보다 작다면 앞에 0을 붙여 두 자리 수로 만들고, 각 자리의 숫자를 더한다. 그 다음, 주어진 수의 가장 오른쪽 자리 수와 앞에서 구한 합의 가장 오른쪽 자리 수를 이어 붙이면 새로운 수를 만들 수 있다. 다음 예를 보자.

26부터 시작한다. 2+6 = 8이다. 새로운 수는 68이다. 6+8 = 14이다. 새로운 수는 84이다. 8+4 = 12이다. 새로운 수는 42이다. 4+2 = 6이다. 새로운 수는 26이다.

위의 예는 4번만에 원래 수로 돌아올 수 있다. 따라서 26의 사이클의 길이는 4이다.

N이 주어졌을 때, N의 사이클의 길이를 구하는 프로그램을 작성하시오.


```python
def my_func(n):
    a = n // 10  # 10으로 나눈 몫
    b = n % 10  # 10으로 나눈 나머지
    c = a + b
    c = c % 10
    return b * 10 + c

n = int(input())
temp = n
count = 1
while my_func(temp) != n:
    count += 1
    temp = my_func(temp)
print(count)
```

    71
    12
    

### 10807: 개수 세기
총 N개의 정수가 주어졌을 때, 정수 v가 몇 개인지 구하는 프로그램을 작성하시오.


```python
_ = input()
nums = list(map(int, input().split()))
n = int(input())
count = 0
for i in nums:
    if i == n:
        count += 1
print(count)
```

    11
    1 4 1 2 4 2 4 2 3 4 4
    5
    0
    




```python
print(list(map(int, input().split())))
```

    1 3 5
    [1, 3, 5]
    

## while loop


You can write while loop with<br>
`while <condition>:`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`code in loop`<br>
`code after loop`

Again, indentation is not optional.


```python
var = 1
while var < 10:
    print(var)
    var += 1
```

    1
    2
    3
    4
    5
    6
    7
    8
    9
    


```python
var = 1
while var != "good bye" :
    var = input("Say something  :")
    print("You entered: {}".format(var))

print("Good bye!")
```

    Say something  :Hello
    You entered: Hello
    Say something  :Hi
    You entered: Hi
    Say something  :good bye
    You entered: good bye
    Good bye!
    

## for loop

You can write for loops with<br>
`for <var> in <list>:`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`code in loop`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`code in loop`<br>
`code after loop`

Again, indentation is not optional.


```python
# Print Fibonacci sequence
F_prev = 0
print(F_prev)
F_curr = 1
print(F_curr)

#for loop with numerical index
for i in range(10):
    F_next = F_prev + F_curr
    F_prev = F_curr
    F_curr = F_next
    print(F_next)
```


```python
#for loop with list
fruit_list = ["apple", "banana", "cherry"]
for fruit in fruit_list:
    print(fruit)
```

Generally, the for loop works with any "iterable" object. (More on this when we talk about objects.)


```python
#for loop with string
for c in "The Best Things in Life are Free":
    print("Current character: {}".format(c))
```

## List comprehension
An intuitive and concise way to create lists.


```python
# ** power symbol
[i**2 for i in range(6)]
```


```python
[0 for _ in range(5)]  #use _ if you don't need the variable
```

Use **if conditionals** to filter out elements


```python
[i**2 for i in range(5) if i%2==0]
```

You can use **multiple for clauses**


```python
[i+j for i in range(2) for j in range(4)]
```


```python
[i+j for j in range(4) for i in range(2)]  #What is the difference?
```


```python
#For loop equivalent to the list comprehension
L = []
for i in range(2):
    for j in range(4):
        L.append(i+j)
print(L)
```


```python
[[i+j for i in range(2)] for j in range(4)]
```


```python
[[i+j for j in range(4)] for i in range(2)]  #what there a difference?
```

__Exercise__ : Use a list comprehension to create:  [[1,2,3],[2,4,6],[3,6,9],[4,8,12]].


```python

```

__Exercise__ : Use a list comprehension to create:[0,0,0,0,1,2,0,2,4,0,3,6,0,4,8,0,5,10].


```python

```
