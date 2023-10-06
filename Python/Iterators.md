An _iterable_ is an object that can return an _iterator_, while an _iterator_ is an object that keeps state and produces the next value when you call `next()` on it.

```python
# Create a list of strings: flash
flash = ['jay garrick', 'barry allen', 'wally west', 'bart allen']
# Print each list item in flash using a for loop
for item in flash:
    print(item)
# Create an iterator for flash: superhero
superhero = iter(flash)
# Print each item from the iterator
print(next(superhero))
print(next(superhero))
print(next(superhero))
print(next(superhero))
```

#### enumerate()
`enumerate()` returns an `enumerate` object that produces a sequence of tuples, and each of the tuples is an _index-value_ pair.
```python
# Create a list of strings: mutants
mutants = ['charles xavier', 
            'bobby drake', 
            'kurt wagner', 
            'max eisenhardt', 
            'kitty pryde']
# Create a list of tuples: mutant_list
mutant_list = list(enumerate(mutants))  
# Print the list of tuples
print(mutant_list)  
# Unpack and print the tuple pairs
for index1,value1 in enumerate(mutants):
    print(index1, value1)  
# Change the start index
for index2,value2 in enumerate(mutants, start=1):
    print(index2, value2)
```

```console
[(0, 'charles xavier'), (1, 'bobby drake'), (2, 'kurt wagner'), (3, 'max eisenhardt'), (4, 'kitty pryde')] 
0 charles xavier 
1 bobby drake 
2 kurt wagner 
3 max eisenhardt 
4 kitty pryde 
1 charles xavier 
2 bobby drake 
3 kurt wagner 
4 max eisenhardt 
5 kitty pryde
```

#### zip()
zip() function is a built-in function and it takes any number of iterables and returns a list of tuples. The ith element of the tuple is created using the ith element from each of the iterables.

```python
listA = [`1, 2, 3, 4]

listB = ['a', 'b', 'c', 'd']

zl = zip(listA, listB)

zl = list(zl)

print(zl)

listC, listD = zip(*zl)

print(listC)

print(listD)

print(listA)

print(listB)
```

```console
[(1, ‘a’), (2, ‘b’), (3, ‘c’), (4, ‘d’)]  
(1, 2, 3, 4, 5)  
(‘a’, ‘b’, ‘c’, ‘d’, ‘e’)  
[1, 2, 3, 4, 5]  
[‘a’, ‘b’, ‘c’, ‘d’, ‘e’]
```

Note that listC and listD are printed as tuples whereas listA and listB are printed as Lists.