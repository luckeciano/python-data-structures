#  Built-in Data Structures

## Lists
* list = []
* [Operations](https://docs.python.org/2/tutorial/datastructures.html) and [Complexity](https://wiki.python.org/moin/TimeComplexity)
* [List Comprehensions](https://docs.python.org/2/tutorial/datastructures.html#list-comprehensions)

## Tuples

* tuple = ()
* Apart from tuples being immutable there is also a semantic distinction that should guide their usage. Tuples are heterogeneous data structures (i.e., their entries have different meanings), while lists are homogeneous sequences. Tuples have structure, lists have order.
* [Reference](https://docs.python.org/2/tutorial/datastructures.html#tuples-and-sequences)


## Sets

* Python also includes a data type for sets. A set is an unordered collection with no duplicate elements. Basic uses include membership testing and eliminating duplicate entries. Set objects also support mathematical operations like union, intersection, difference, and symmetric difference.
* There is *set comprehensions*.
* [Operations and Complexity](https://wiki.python.org/moin/TimeComplexity)
* [List of operations by Hackerrank exercise](https://www.hackerrank.com/challenges/symmetric-difference/problem)

## Dictionaries
* A mapping object maps hashable values to arbitrary objects.
* [Operations](https://docs.python.org/2/library/stdtypes.html#mapping-types-dict) and [Complexity](https://wiki.python.org/moin/TimeComplexity)


#  Collections

## Counter
* A counter is a container that stores elements as dictionary keys, and their counts are stored as dictionary values.
* Usage example:
     ```sh
    >>> from collections import Counter
    >>> 
    >>> myList = [1,1,2,3,4,5,3,2,3,4,2,1,2,3]
    >>> print Counter(myList)
    Counter({2: 4, 3: 4, 1: 3, 4: 2, 5: 1})
    >>>
    >>> print Counter(myList).items()
    [(1, 3), (2, 4), (3, 4), (4, 2), (5, 1)]
    >>> 
    >>> print Counter(myList).keys()
    [1, 2, 3, 4, 5]
    >>> 
    >>> print Counter(myList).values()
    [3, 4, 4, 2, 1]
    ```

## DefaultDict 

* The defaultdict tool is a container in the collections class of Python. It's similar to the usual dictionary (dict) container, but the only difference is that a defaultdict will have a default value if that key has not been set yet. If you didn't use a defaultdict you'd have to check to see if that key exists, and if it doesn't, set it to what you want. 
* Usage example:
     ```sh
    from collections import defaultdict
    d = defaultdict(list)
    d['python'].append("awesome")
    d['something-else'].append("not relevant")
    d['python'].append("language")
    for i in d.items():
        print i
    
    This prints:
    ('python', ['awesome', 'language'])
    ('something-else', ['not relevant'])
    ```

## Namedtuple

* Basically, namedtuples are easy to create, lightweight object types. 
They turn tuples into convenient containers for simple tasks. 
With namedtuples, you don’t have to use integer indices for accessing members of a tuple.
* Usage example:
     ```sh
    >>> from collections import namedtuple
    >>> Point = namedtuple('Point','x,y')
    >>> pt1 = Point(1,2)
    >>> pt2 = Point(3,4)
    >>> dot_product = ( pt1.x * pt2.x ) +( pt1.y * pt2.y )
    >>> print dot_product
    11
    ```
     ```sh
    >>> from collections import namedtuple
    >>> Car = namedtuple('Car','Price Mileage Colour Class')
    >>> xyz = Car(Price = 100000, Mileage = 30, Colour = 'Cyan', Class = 'Y')
    >>> print xyz
    Car(Price=100000, Mileage=30, Colour='Cyan', Class='Y')
    >>> print xyz.Class
    Y
    ```
## OrderedDict

* An OrderedDict is a dictionary that remembers the order of the keys that were inserted first. If a new entry overwrites an existing entry, the original insertion position is left unchanged.
* Example usage:
    ```sh
    >>> from collections import OrderedDict
    >>> 
    >>> ordinary_dictionary = {}
    >>> ordinary_dictionary['a'] = 1
    >>> ordinary_dictionary['b'] = 2
    >>> ordinary_dictionary['c'] = 3
    >>> ordinary_dictionary['d'] = 4
    >>> ordinary_dictionary['e'] = 5
    >>> 
    >>> print ordinary_dictionary
    {'a': 1, 'c': 3, 'b': 2, 'e': 5, 'd': 4}
    >>> 
    >>> ordered_dictionary = OrderedDict()
    >>> ordered_dictionary['a'] = 1
    >>> ordered_dictionary['b'] = 2
    >>> ordered_dictionary['c'] = 3
    >>> ordered_dictionary['d'] = 4
    >>> ordered_dictionary['e'] = 5
    >>> 
    >>> print ordered_dictionary
    OrderedDict([('a', 1), ('b', 2), ('c', 3), ('d', 4), ('e', 5)])
    ```
## deque

* A deque is a double-ended queue. It can be used to add or remove elements from both ends. Deques support thread safe, memory efficient appends and pops from either side of the deque with approximately the same O(1)  performance in either direction.
* [Operations](https://docs.python.org/2/library/collections.html#deque-objects) and [Recipes](https://docs.python.org/2.7/library/collections.html#deque-recipes)
* Example usage:
    ```sh
    >>> from collections import deque
    >>> d = deque()
    >>> d.append(1)
    >>> print d
    deque([1])
    >>> d.appendleft(2)
    >>> print d
    deque([2, 1])
    >>> d.clear()
    >>> print d
    deque([])
    >>> d.extend('1')
    >>> print d
    deque(['1'])
    >>> d.extendleft('234')
    >>> print d
    deque(['4', '3', '2', '1'])
    >>> d.count('1')
    1
    >>> d.pop()
    '1'
    >>> print d
    deque(['4', '3', '2'])
    >>> d.popleft()
    '4'
    >>> print d
    deque(['3', '2'])
    >>> d.extend('7896')
    >>> print d
    deque(['3', '2', '7', '8', '9', '6'])
    >>> d.remove('2')
    >>> print d
    deque(['3', '7', '8', '9', '6'])
    >>> d.reverse()
    >>> print d
    deque(['6', '9', '8', '7', '3'])
    >>> d.rotate(3)
    >>> print d
    deque(['8', '7', '3', '6', '9'])
    ```

#  itertools

## combinations

* itertools.combinations(iterable, r) 
* This tool returns the  length subsequences of elements from the input iterable.
Combinations are emitted in lexicographic sorted order. So, if the input iterable is sorted, the combination tuples will be produced in sorted order.
* Example usage:
     ```sh
    >>> from itertools import combinations
    >>> 
    >>> print list(combinations('12345',2))
    [('1', '2'), ('1', '3'), ('1', '4'), ('1', '5'), ('2', '3'), ('2', '4'), ('2', '5'), ('3', '4'), ('3', '5'), ('4', '5')]
    >>> 
    >>> A = [1,1,3,3,3]
    >>> print list(combinations(A,4))
    [(1, 1, 3, 3), (1, 1, 3, 3), (1, 1, 3, 3), (1, 3, 3, 3), (1, 3, 3, 3)]
    ```
    
## combinations_with_replacement
* itertools.combinations_with_replacement(iterable, r) 
* This tool returns  length subsequences of elements from the input iterable allowing individual elements to be repeated more than once.
Combinations are emitted in lexicographic sorted order. So, if the input iterable is sorted, the combination tuples will be produced in sorted order.
* Example usage: 
    ```sh
    >>> from itertools import combinations_with_replacement
    >>> 
    >>> print list(combinations_with_replacement('12345',2))
    [('1', '1'), ('1', '2'), ('1', '3'), ('1', '4'), ('1', '5'), ('2', '2'), ('2', '3'), ('2', '4'), ('2', '5'), ('3', '3'), ('3', '4'), ('3', '5'), ('4', '4'), ('4', '5'), ('5', '5')]
    >>> 
    >>> A = [1,1,3,3,3]
    >>> print list(combinations(A,2))
    [(1, 1), (1, 3), (1, 3), (1, 3), (1, 3), (1, 3), (1, 3), (3, 3), (3, 3), (3, 3)]
    ```


# numpy

* initialize a numpy array from list
    ```sh
    import numpy

    a = numpy.array([1,2,3,4,5])
    print a[1]          #2
    
    b = numpy.array([1,2,3,4,5],float)
    print b[1]          #2.0
    ```
    
* shape and reshape

    ```sh
    import numpy

    my__1D_array = numpy.array([1, 2, 3, 4, 5])
    print my_1D_array.shape     #(5,) -> 5 rows and 0 columns
    
    my__2D_array = numpy.array([[1, 2],[3, 4],[6,5]])
    print my_2D_array.shape     #(3, 2) -> 3 rows and 2 columns 
    ```

    ```sh
    import numpy

    my_array = numpy.array([1,2,3,4,5,6])
    print numpy.reshape(my_array,(3,2))
    

    #Output
    [[1 2]
    [3 4]
    [5 6]]
    ```

* transpose
    ```sh
    import numpy
    
    my_array = numpy.array([[1,2,3],
                            [4,5,6]])
    print numpy.transpose(my_array)
    
    #Output
    [[1 4]
     [2 5]
     [3 6]]
     ```

* flatten
    ```sh
    import numpy

    my_array = numpy.array([[1,2,3],
                            [4,5,6]])
    print my_array.flatten()
    
    #Output
    [1 2 3 4 5 6]
    ```
    
* concatenate
    ```sh
    import numpy

    array_1 = numpy.array([1,2,3])
    array_2 = numpy.array([4,5,6])
    array_3 = numpy.array([7,8,9])
    
    print numpy.concatenate((array_1, array_2, array_3))    
    
    #Output
    [1 2 3 4 5 6 7 8 9]
    ```
   
   ```sh 
    import numpy

    array_1 = numpy.array([[1,2,3],[0,0,0]])
    array_2 = numpy.array([[0,0,0],[7,8,9]])
    
    print numpy.concatenate((array_1, array_2), axis = 1)   
    
    #Output
    [[1 2 3 0 0 0]
     [0 0 0 7 8 9]]  
     ```

* zeros
    ```sh
    import numpy

    print numpy.zeros((1,2))                    #Default type is float
    #Output : [[ 0.  0.]] 
    
    print numpy.zeros((1,2), dtype = numpy.int) #Type changes to int
    #Output : [[0 0]]
    ```
    
* ones

    ```sh
    import numpy

    print numpy.ones((1,2))                    #Default type is float
    #Output : [[ 1.  1.]] 
    
    print numpy.ones((1,2), dtype = numpy.int) #Type changes to int
    #Output : [[1 1]]   
    ```
* identity
    * The identity tool returns an identity array. An identity array is a square matrix with all the main diagonal elements as 1 and the rest as 0. The default type of elements is float.
    ```sh
    import numpy
    print numpy.identity(3) #3 is for  dimension 3 X 3
    
    #Output
    [[ 1.  0.  0.]
     [ 0.  1.  0.]
     [ 0.  0.  1.]]
     ```
     
* eye
    * The eye tool returns a 2-D array with 1's as the diagonal and 0's elsewhere. The diagonal can be main, upper or lower depending on the optional parameter k. A positive k is for the upper diagonal, a negative  k is for the lower, and a   0 k (default) is for the main diagonal.
    ```sh
    import numpy
    print numpy.eye(8, 7, k = 1)    # 8 X 7 Dimensional array with first upper diagonal 1.
    
    #Output
    [[ 0.  1.  0.  0.  0.  0.  0.]
     [ 0.  0.  1.  0.  0.  0.  0.]
     [ 0.  0.  0.  1.  0.  0.  0.]
     [ 0.  0.  0.  0.  1.  0.  0.]
     [ 0.  0.  0.  0.  0.  1.  0.]
     [ 0.  0.  0.  0.  0.  0.  1.]
     [ 0.  0.  0.  0.  0.  0.  0.]
     [ 0.  0.  0.  0.  0.  0.  0.]]
    
    print numpy.eye(8, 7, k = -2)   # 8 X 7 Dimensional array with second lower diagonal 1.
    ```
* mathematics
    ```sh
    import numpy

    a = numpy.array([1,2,3,4], float)
    b = numpy.array([5,6,7,8], float)
    
    print a + b                     #[  6.   8.  10.  12.]
    print numpy.add(a, b)           #[  6.   8.  10.  12.]
    
    print a - b                     #[-4. -4. -4. -4.]
    print numpy.subtract(a, b)      #[-4. -4. -4. -4.]
    
    print a * b                     #[  5.  12.  21.  32.]
    print numpy.multiply(a, b)      #[  5.  12.  21.  32.]
    
    print a / b                     #[ 0.2         0.33333333  0.42857143  0.5       ]
    print numpy.divide(a, b)        #[ 0.2         0.33333333  0.42857143  0.5       ]
    
    print a % b                     #[ 1.  2.  3.  4.]
    print numpy.mod(a, b)           #[ 1.  2.  3.  4.]
    
    print a**b                      #[  1.00000000e+00   6.40000000e+01   2.18700000e+03   6.55360000e+04]
    print numpy.power(a, b)         #[  1.00000000e+00   6.40000000e+01   2.18700000e+03   6.55360000e+04]
    ```
    
* floor, ceil, rint

    * floor: The tool floor returns the floor of the input element-wise. 
    ```sh
    import numpy

    my_array = numpy.array([1.1, 2.2, 3.3, 4.4, 5.5, 6.6, 7.7, 8.8, 9.9])
    print numpy.floor(my_array)         #[ 1.  2.  3.  4.  5.  6.  7.  8.  9.]
    ```
    
    * ceil: The tool ceil returns the ceiling of the input element-wise. 
    ```sh
    import numpy

    my_array = numpy.array([1.1, 2.2, 3.3, 4.4, 5.5, 6.6, 7.7, 8.8, 9.9])
    print numpy.ceil(my_array)          #[  2.   3.   4.   5.   6.   7.   8.   9.  10.]
    ```
    
    * rint: The rint tool rounds to the nearest integer of input element-wise.
    ```sh
    import numpy

    my_array = numpy.array([1.1, 2.2, 3.3, 4.4, 5.5, 6.6, 7.7, 8.8, 9.9])
    print numpy.rint(my_array)          #[  1.   2.   3.   4.   6.   7.   8.   9.  10.]
    ```
* sum, prod
    * sum: The sum tool returns the sum of array elements over a given axis.
    ```sh
    import numpy

    my_array = numpy.array([ [1, 2], [3, 4] ])
    
    print numpy.sum(my_array, axis = 0)         #Output : [4 6]
    print numpy.sum(my_array, axis = 1)         #Output : [3 7]
    print numpy.sum(my_array, axis = None)      #Output : 10
    print numpy.sum(my_array)                   #Output : 10
    ```
    
    * prod: The prod tool returns the product of array elements over a given axis.
    ```sh
    import numpy

    my_array = numpy.array([ [1, 2], [3, 4] ])
    
    print numpy.prod(my_array, axis = 0)            #Output : [3 8]
    print numpy.prod(my_array, axis = 1)            #Output : [ 2 12]
    print numpy.prod(my_array, axis = None)         #Output : 24
    print numpy.prod(my_array)                      #Output : 24
    ```
* mean, std, var
    ```sh
    import numpy

    my_array = numpy.array([ [1, 2], [3, 4] ])
    
    print numpy.mean(my_array, axis = 0)        #Output : [ 2.  3.]
    print numpy.mean(my_array, axis = 1)        #Output : [ 1.5  3.5]
    print numpy.mean(my_array, axis = None)     #Output : 2.5
    print numpy.mean(my_array)                  #Output : 2.5
    
    print numpy.var(my_array, axis = 0)         #Output : [ 1.  1.]
    print numpy.var(my_array, axis = 1)         #Output : [ 0.25  0.25]
    print numpy.var(my_array, axis = None)      #Output : 1.25
    print numpy.var(my_array)                   #Output : 1.25
    
    print numpy.std(my_array, axis = 0)         #Output : [ 1.  1.]
    print numpy.std(my_array, axis = 1)         #Output : [ 0.5  0.5]
    print numpy.std(my_array, axis = None)      #Output : 1.11803398875
    print numpy.std(my_array)                   #Output : 1.11803398875
    ```

* min, max
    ```sh
    import numpy

    my_array = numpy.array([[2, 5], 
                            [3, 7],
                            [1, 3],
                            [4, 0]])
    
    print numpy.min(my_array, axis = 0)         #Output : [1 0]
    print numpy.min(my_array, axis = 1)         #Output : [2 3 1 0]
    print numpy.min(my_array, axis = None)      #Output : 0
    print numpy.min(my_array)                   #Output : 0
    
    print numpy.max(my_array, axis = 0)         #Output : [4 7]
    print numpy.max(my_array, axis = 1)         #Output : [5 7 3 4]
    print numpy.max(my_array, axis = None)      #Output : 7
    print numpy.max(my_array)                   #Output : 7
    ```
    
* dot, cross, inner, outer
    ```sh
    import numpy

    A = numpy.array([ 1, 2 ])
    B = numpy.array([ 3, 4 ])
    
    print numpy.dot(A, B)       #Output : 11
    
    print numpy.cross(A, B)     #Output : -2
    
    A = numpy.array([0, 1])
    B = numpy.array([3, 4])
    
    print numpy.inner(A, B)     #Output : 4
    
    print numpy.outer(A, B)     #Output : [[0 0]
                                #          [3 4]]
    ```
* polynomials
    * poly: The poly tool returns the coefficients of a polynomial with the given sequence of roots.
    ```sh 
    print numpy.poly([-1, 1, 1, 10])        #Output : [  1 -11   9  11 -10] 
    ```
    * roots: The roots tool returns the roots of a polynomial with the given coefficients.
    ```sh 
    print numpy.roots([1, 0, -1])           #Output : [-1.  1.]
    ```
    * polyint: The polyint tool returns an antiderivative (indefinite integral) of a polynomial.
    ```sh
    print numpy.polyint([1, 1, 1])          #Output : [ 0.33333333  0.5         1.          0.        ]
    ```
    * polyder: The polyder tool returns the derivative of the specified order of a polynomial.
    ```sh
    print numpy.polyder([1, 1, 1, 1])       #Output : [3 2 1]
    ```
    * polyval: The polyval tool evaluates the polynomial at specific value.
    ```sh
    print numpy.polyval([1, -2, 0, 2], 4)   #Output : 34
    ```
    * polyfit: The polyfit tool fits a polynomial of a specified order to a set of data using a least-squares approach.
    ```sh
    print numpy.polyfit([0,1,-1, 2, -2], [0,1,1, 4, 4], 2)
    #Output : [  1.00000000e+00   0.00000000e+00  -3.97205465e-16]
    ```
    * The functions polyadd, polysub, polymul, and polydiv also handle proper addition, subtraction, multiplication, and division of polynomial coefficients, respectively.
    
* Linear Algebra
    * linalg.det: The linalg.det tool computes the determinant of an array.  
    ```sh
    print numpy.linalg.det([[1 , 2], [2, 1]])       #Output : -3.0
    ```
    
    * linalg.eig: The linalg.eig computes the eigenvalues and right eigenvectors of a square array.
    ```sh
    vals, vecs = numpy.linalg.eig([[1 , 2], [2, 1]])
    print vals                                      #Output : [ 3. -1.]
    print vecs                                      #Output : [[ 0.70710678 -0.70710678]
                                                    #          [ 0.70710678  0.70710678]]
    ```
    * linalg.inv: The linalg.inv tool computes the (multiplicative) inverse of a matrix.
    ```sh
    print numpy.linalg.inv([[1 , 2], [2, 1]])       #Output : [[-0.33333333  0.66666667]
                                                #          [ 0.66666667 -0.33333333]]
    ```
    * [Othe great operations from linalg](https://docs.scipy.org/doc/numpy/reference/routines.linalg.html)
# Credits

All the credits for HackerRank platform! :)




