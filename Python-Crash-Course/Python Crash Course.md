
# Python Crash Course

Please note, this is not meant to be a comprehensive overview of Python or programming in general, if you have no programming experience, you should probably take my other course: [Complete Python Bootcamp](https://www.udemy.com/complete-python-bootcamp/?couponCode=PY20) instead.

**This notebook is just a code reference for the videos, no written explanations here**

This notebook will just go through the basic topics in order:

* Data types
    * Numbers
    * Strings
    * Printing
    * Lists
    * Dictionaries
    * Booleans
    * Tuples 
    * Sets
* Comparison Operators
* if,elif, else Statements
* for Loops
* while Loops
* range()
* list comprehension
* functions
* lambda expressions
* map and filter
* methods
____

## Data types

### Numbers


```python
1 + 1
```




    2




```python
1 * 3
```




    3




```python
1 / 2
```




    0.5




```python
2 ** 4
```




    16




```python
4 % 2
```




    0




```python
5 % 2
```




    1




```python
(2 + 3) * (5 + 5)
```




    50



### Variable Assignment


```python
# Can not start with number or special characters
name_of_var = 2
```


```python
x = 2
y = 3
```


```python
z = x + y
```


```python
z
```




    5



### Strings


```python
'single quotes'
```




    'single quotes'




```python
"double quotes"
```




    'double quotes'




```python
" wrap lot's of other quotes"
```




    " wrap lot's of other quotes"



### Printing


```python
x = 'hello'
```


```python
x
```




    'hello'




```python
print(x)
```

    hello
    


```python
num = 12
name = 'Sam'
```


```python
print('My number is: {one}, and my name is: {two}'.format(one=num,two=name))
```

    My number is: 12, and my name is: Sam
    


```python
print('My number is: {}, and my name is: {}'.format(num,name))
```

    My number is: 12, and my name is: Sam
    

### Lists


```python
[1,2,3]
```




    [1, 2, 3]




```python
['hi',1,[1,2]]
```




    ['hi', 1, [1, 2]]




```python
my_list = ['a','b','c']
```


```python
my_list.append('d')
```


```python
my_list
```




    ['a', 'b', 'c', 'd']




```python
my_list[0]
```




    'a'




```python
my_list[1]
```




    'b'




```python
my_list[1:]
```




    ['b', 'c', 'd']




```python
my_list[:1]
```




    ['a']




```python
my_list[0] = 'NEW'
```


```python
my_list
```




    ['NEW', 'b', 'c', 'd']




```python
nest = [1,2,3,[4,5,['target']]]
```


```python
nest[3]
```




    [4, 5, ['target']]




```python
nest[3][2]
```




    ['target']




```python
nest[3][2][0]
```




    'target'



### Dictionaries


```python
d = {'key1':'item1','key2':'item2'}
```


```python
d
```




    {'key1': 'item1', 'key2': 'item2'}




```python
d['key1']
```




    'item1'



### Booleans


```python
True
```




    True




```python
False
```




    False



### Tuples 


```python
t = (1,2,3)
```


```python
t[0]
```




    1




```python
t[0] = 'NEW'
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-47-93bfe9be1549> in <module>()
    ----> 1 t[0] = 'NEW'
    

    TypeError: 'tuple' object does not support item assignment


### Sets


```python
{1,2,3}
```




    {1, 2, 3}




```python
{1,2,3,1,2,1,2,3,3,3,3,2,2,2,1,1,2}
```




    {1, 2, 3}



## Comparison Operators


```python
1 > 2
```




    False




```python
1 < 2
```




    True




```python
1 >= 1
```




    True




```python
1 <= 4
```




    True




```python
1 == 1
```




    True




```python
'hi' == 'bye'
```




    False



## Logic Operators


```python
(1 > 2) and (2 < 3)
```




    False




```python
(1 > 2) or (2 < 3)
```




    True




```python
(1 == 2) or (2 == 3) or (4 == 4)
```




    True



## if,elif, else Statements


```python
if 1 < 2:
    print('Yep!')
```

    Yep!
    


```python
if 1 < 2:
    print('yep!')
```

    yep!
    


```python
if 1 < 2:
    print('first')
else:
    print('last')
```

    first
    


```python
if 1 > 2:
    print('first')
else:
    print('last')
```

    last
    


```python
if 1 == 2:
    print('first')
elif 3 == 3:
    print('middle')
else:
    print('Last')
```

    middle
    

## for Loops


```python
seq = [1,2,3,4,5]
```


```python
for item in seq:
    print(item)
```

    1
    2
    3
    4
    5
    


```python
for item in seq:
    print('Yep')
```

    Yep
    Yep
    Yep
    Yep
    Yep
    


```python
for jelly in seq:
    print(jelly+jelly)
```

    2
    4
    6
    8
    10
    

## while Loops


```python
i = 1
while i < 5:
    print('i is: {}'.format(i))
    i = i+1
```

    i is: 1
    i is: 2
    i is: 3
    i is: 4
    

## range()


```python
range(5)
```




    range(0, 5)




```python
for i in range(5):
    print(i)
```

    0
    1
    2
    3
    4
    


```python
list(range(5))
```




    [0, 1, 2, 3, 4]



## list comprehension


```python
x = [1,2,3,4]
```


```python
out = []
for item in x:
    out.append(item**2)
print(out)
```

    [1, 4, 9, 16]
    


```python
[item**2 for item in x]
```




    [1, 4, 9, 16]



## functions


```python
def my_func(param1='default'):
    """
    Docstring goes here.
    """
    print(param1)
```


```python
my_func
```




    <function __main__.my_func>




```python
my_func()
```

    default
    


```python
my_func('new param')
```

    new param
    


```python
my_func(param1='new param')
```

    new param
    


```python
def square(x):
    return x**2
```


```python
out = square(2)
```


```python
print(out)
```

    4
    

## lambda expressions


```python
def times2(var):
    return var*2
```


```python
times2(2)
```




    4




```python
lambda var: var*2
```




    <function __main__.<lambda>>



## map and filter


```python
seq = [1,2,3,4,5]
```


```python
map(times2,seq)
```




    <map at 0x16a0fad8710>




```python
list(map(times2,seq))
```




    [2, 4, 6, 8, 10]




```python
list(map(lambda var: var*2,seq))
```




    [2, 4, 6, 8, 10]




```python
filter(lambda item: item%2 == 0,seq)
```




    <filter at 0x16a0fad85c0>




```python
list(filter(lambda item: item%2 == 0,seq))
```




    [2, 4]



## methods


```python
st = 'hello my name is Sam'
```


```python
st.lower()
```




    'hello my name is sam'




```python
st.upper()
```




    'HELLO MY NAME IS SAM'




```python
st.split()
```




    ['hello', 'my', 'name', 'is', 'Sam']




```python
tweet = 'Go Sports! #Sports'
```


```python
tweet.split('#')
```




    ['Go Sports! ', 'Sports']




```python
tweet.split('#')[1]
```




    'Sports'




```python
d
```




    {'key1': 'item1', 'key2': 'item2'}




```python
d.keys()
```




    dict_keys(['key1', 'key2'])




```python
d.items()
```




    dict_items([('key1', 'item1'), ('key2', 'item2')])




```python
lst = [1,2,3]
```


```python
lst.pop()
```




    3




```python
lst
```




    [1, 2]




```python
'x' in [1,2,3]
```




    False




```python
'x' in ['x','y','z']
```




    True



# Great Job!
