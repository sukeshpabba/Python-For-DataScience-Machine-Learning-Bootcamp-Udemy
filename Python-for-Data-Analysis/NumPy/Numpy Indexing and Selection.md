
___

<a href='http://www.pieriandata.com'> <img src='../Pierian_Data_Logo.png' /></a>
___

# NumPy Indexing and Selection

In this lecture we will discuss how to select elements or groups of elements from an array.


```python
import numpy as np
```


```python
#Creating sample array
arr = np.arange(0,11)
```


```python
#Show
arr
```




    array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10])



## Bracket Indexing and Selection
The simplest way to pick one or some elements of an array looks very similar to python lists:


```python
#Get a value at an index
arr[8]
```




    8




```python
#Get values in a range
arr[1:5]
```




    array([1, 2, 3, 4])




```python
#Get values in a range
arr[0:5]
```




    array([0, 1, 2, 3, 4])



## Broadcasting

Numpy arrays differ from a normal Python list because of their ability to broadcast:


```python
#Setting a value with index range (Broadcasting)
arr[0:5]=100

#Show
arr
```




    array([100, 100, 100, 100, 100,   5,   6,   7,   8,   9,  10])




```python
# Reset array, we'll see why I had to reset in  a moment
arr = np.arange(0,11)

#Show
arr
```




    array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10])




```python
#Important notes on Slices
slice_of_arr = arr[0:6]

#Show slice
slice_of_arr
```




    array([0, 1, 2, 3, 4, 5])




```python
#Change Slice
slice_of_arr[:]=99

#Show Slice again
slice_of_arr
```




    array([99, 99, 99, 99, 99, 99])



Now note the changes also occur in our original array!


```python
arr
```




    array([99, 99, 99, 99, 99, 99,  6,  7,  8,  9, 10])



Data is not copied, it's a view of the original array! This avoids memory problems!


```python
#To get a copy, need to be explicit
arr_copy = arr.copy()

arr_copy
```




    array([99, 99, 99, 99, 99, 99,  6,  7,  8,  9, 10])



## Indexing a 2D array (matrices)

The general format is **arr_2d[row][col]** or **arr_2d[row,col]**. I recommend usually using the comma notation for clarity.


```python
arr_2d = np.array(([5,10,15],[20,25,30],[35,40,45]))

#Show
arr_2d
```




    array([[ 5, 10, 15],
           [20, 25, 30],
           [35, 40, 45]])




```python
#Indexing row
arr_2d[1]

```




    array([20, 25, 30])




```python
# Format is arr_2d[row][col] or arr_2d[row,col]

# Getting individual element value
arr_2d[1][0]
```




    20




```python
# Getting individual element value
arr_2d[1,0]
```




    20




```python
# 2D array slicing

#Shape (2,2) from top right corner
arr_2d[:2,1:]
```




    array([[10, 15],
           [25, 30]])




```python
#Shape bottom row
arr_2d[2]
```




    array([35, 40, 45])




```python
#Shape bottom row
arr_2d[2,:]
```




    array([35, 40, 45])



### Fancy Indexing

Fancy indexing allows you to select entire rows or columns out of order,to show this, let's quickly build out a numpy array:


```python
#Set up matrix
arr2d = np.zeros((10,10))
```


```python
#Length of array
arr_length = arr2d.shape[1]
```


```python
#Set up array

for i in range(arr_length):
    arr2d[i] = i
    
arr2d
```




    array([[0., 0., 0., 0., 0., 0., 0., 0., 0., 0.],
           [1., 1., 1., 1., 1., 1., 1., 1., 1., 1.],
           [2., 2., 2., 2., 2., 2., 2., 2., 2., 2.],
           [3., 3., 3., 3., 3., 3., 3., 3., 3., 3.],
           [4., 4., 4., 4., 4., 4., 4., 4., 4., 4.],
           [5., 5., 5., 5., 5., 5., 5., 5., 5., 5.],
           [6., 6., 6., 6., 6., 6., 6., 6., 6., 6.],
           [7., 7., 7., 7., 7., 7., 7., 7., 7., 7.],
           [8., 8., 8., 8., 8., 8., 8., 8., 8., 8.],
           [9., 9., 9., 9., 9., 9., 9., 9., 9., 9.]])



Fancy indexing allows the following


```python
arr2d[[2,4,6,8]]
```




    array([[ 2.,  2.,  2.,  2.,  2.,  2.,  2.,  2.,  2.,  2.],
           [ 4.,  4.,  4.,  4.,  4.,  4.,  4.,  4.,  4.,  4.],
           [ 6.,  6.,  6.,  6.,  6.,  6.,  6.,  6.,  6.,  6.],
           [ 8.,  8.,  8.,  8.,  8.,  8.,  8.,  8.,  8.,  8.]])




```python
#Allows in any order
arr2d[[6,4,2,7]]
```




    array([[ 6.,  6.,  6.,  6.,  6.,  6.,  6.,  6.,  6.,  6.],
           [ 4.,  4.,  4.,  4.,  4.,  4.,  4.,  4.,  4.,  4.],
           [ 2.,  2.,  2.,  2.,  2.,  2.,  2.,  2.,  2.,  2.],
           [ 7.,  7.,  7.,  7.,  7.,  7.,  7.,  7.,  7.,  7.]])



## More Indexing Help
Indexing a 2d matrix can be a bit confusing at first, especially when you start to add in step size. Try google image searching NumPy indexing to fins useful images, like this one:

<img src= 'http://memory.osu.edu/classes/python/_images/numpy_indexing.png' width=500/>

## Selection

Let's briefly go over how to use brackets for selection based off of comparison operators.


```python
arr = np.arange(1,11)
arr
```




    array([ 1,  2,  3,  4,  5,  6,  7,  8,  9, 10])




```python
arr > 4
```




    array([False, False, False, False,  True,  True,  True,  True,  True,  True], dtype=bool)




```python
bool_arr = arr>4
```


```python
bool_arr
```




    array([False, False, False, False,  True,  True,  True,  True,  True,  True], dtype=bool)




```python
arr[bool_arr]
```




    array([ 5,  6,  7,  8,  9, 10])




```python
arr[arr>2]
```




    array([ 3,  4,  5,  6,  7,  8,  9, 10])




```python
x = 2
arr[arr>x]
```




    array([ 3,  4,  5,  6,  7,  8,  9, 10])



# Great Job!

