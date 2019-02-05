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

## Dictionaries
* A mapping object maps hashable values to arbitrary objects.
* [Operations](https://docs.python.org/2/library/stdtypes.html#mapping-types-dict) and [Complexity](https://wiki.python.org/moin/TimeComplexity)


# Collections

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

# Credits

All the credits for HackerRank platform! :)




