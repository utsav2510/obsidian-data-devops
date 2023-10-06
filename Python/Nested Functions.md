Functions defined inside another function is called nested function.
```python
# Define three_shouts
def three_shouts(word1, word2, word3):
    """Returns a tuple of strings
    concatenated with '!!!'."""
    # Define inner
    def inner(word):
        """Returns a string concatenated with '!!!'."""
        return word + '!!!'  
    # Return a tuple of strings
    return (inner(word1), inner(word2), inner(word3))  
# Call three_shouts() and print
print(three_shouts('a', 'b', 'c')
# ('a!!!', 'b!!!', 'c!!!')
```

The nested or inner function remembers the state of its enclosing scope when called. Thus, anything defined locally in the enclosing scope is available to the inner function even when the outer function has finished execution.

### Closures
Closures are dynamically created functions that are returned by other functions. Their main feature is that they have full access to the variables and names defined in the local namespace where the closure was created, even though the enclosing function has returned and finished executing.

In Python, when you return an inner function object, the interpreter packs the function along with its containing environment or closure. The function object keeps a snapshot of all the variables and names defined in its containing scope. To define a closure, you need to take three steps:

1. Create an inner function.
2. Reference variables from the enclosing function.
3. Return the inner function.

With this basic knowledge, you can start creating your closures right away and take advantage of their main feature: **retaining state** between function calls.

```python
x = 10
y = 10
# Define echo
def echo(n):
    """Return the inner_echo function."""
    global x
    x += 1
    z = 1
    # Define inner_echo
    def inner_echo(word1):
        """Concatenate n copies of word1."""
        global y
        echo_word = word1 * n
        y += 1
        nonlocal z
        z += 1
        print("n = ",str(n),", x = ",str(x),", y =" + str(y), ", z =" + str(z))
        return echo_word  
    # Return inner_echo
    return inner_echo  
  
twice = echo(2)
print("First call: Calling twice before defining thrice.")
print(twice('twice1') + '\n')

thrice = echo(3)
print("First call: Calling twice after defining thrice.")
print(twice('twice2')+ '\n')
print("Calling thrice: ")
print(thrice('thrice'))
```

The above program will output:
```console
First call: Calling twice before defining thrice.
n =  2 , x =  11 , y =11 , z =2
twice1twice1

First call: Calling twice after defining thrice.
n =  2 , x =  12 , y =12 , z =3
twice2twice2

Calling thrice:
n =  3 , x =  12 , y =13 , z =2
thricethricethrice
```

where 
- n is as defined while calling the outer function echo,
- x is incremented every time the outer function echo is called
- y is incremented every time the inner function inner_echo is called
- z shows how the variable retains its state in the closure. It is initialized every time outer function echo is called. It has different values for the twice and thrice.  