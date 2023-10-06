**Parameters:** When a function is defined we define the parameter that can be passed to it.
**Arguments:** When a function is called we pass the values corresponding to the parameters defined called as  arguments.

```python
# Defining a function
def square(value1,value2): #1
	"""Return the value1 raised to power value2.""" #2
    new_value = value1 ** value2 #3
    return new_value #4

x = square(4,2)
print(x) # will print 16.
```

1. Function definition starts with def keywork followed by function name and parameters. 
2. The docstring surrounded by 3 quotes defines what the function does. Useful for documentation.
3. Perform operations inside a function.
4. Return some value from the function
5. All the lines inside the function should be indented.

#### Multiple Return values
Functions can have multiple return values using [[Tuples|Tuples]] as shown below:

```python
# Define shout_all with parameters word1 and word2
def shout_all(word1, word2):
    # Concatenate word1 with '!!!': shout1
    shout1 = word1 + '!!!'
    # Concatenate word2 with '!!!': shout2
    shout2 = word2 + '!!!'
    # Construct a tuple with shout1 and shout2: shout_words
    shout_words = (shout1,shout2)  
    # Return shout_words
    return shout_words  
# Pass 'congratulations' and 'you' to shout_all(): yell1, yell2
yell1, yell2 = shout_all('congratulations','you') 
# Print yell1 and yell2
print(yell1)
print(yell2)
```

#### Scope of variables in functions
1. **Global Scope:** Defined in the main body of the script.
2. **Local Scope:** Defined inside the body of the functions.
3. **Built-in scope:** names in the pre-defined built-ins module

**Scope Search Order** (LEGB Rule) 
- **L**ocal Scope
- **E**nclosing Functions ([[Python/Functions#Nested Functions|Nested functions]])
- **G**lobal Scope
- **B**uilt In scope

To access global variable inside the function as local variable we can use the global keyword as shown below. If the global keyword is not used then the variable will remain unchanged in the global scope i.e. outside the function.
```python
new_val = 10
def square(val): 
	"""Return the val raised to power 2."""
    new_value = val ** 2
    return new_value

x = square(4)
print(x) # will print 16 and will not update the new_value variable to 16 in global scope.
```

Using **global** keyword like below will alter the variable value in global scope.
```python
new_val = 10
def square(val): 
	"""Return the val raised to power 2."""
	global new_val 
    new_value = val ** 2
    return new_value

x = square(4)
print(x) # will print 16 and update the new_value variable to 16 in global scope.
```

#### Nested Functions
[[Nested Functions]]

#### Default Arguments

Default arguments will take the default value if the corresponding argument is not passed.

```python
# Define shout_echo
def shout_echo(word1, echo=1):
    """Concatenate echo copies of word1 and three
     exclamation marks at the end of the string."""  
    # Concatenate echo copies of word1 using *: echo_word
    echo_word = word1 * echo  
    # Concatenate '!!!' to echo_word: shout_word
    shout_word = echo_word + '!!!'  
    # Return shout_word
    return shout_word  
# Call shout_echo() with "Hey": no_echo
no_echo = shout_echo("Hey")  
# Call shout_echo() with "Hey" and echo=5: with_echo
with_echo = shout_echo("Hey",5)  
# Print no_echo and with_echo
print(no_echo)
print(with_echo)
#Hey!!! 
#HeyHeyHeyHeyHey!!!
```

#### Flexible Arguments
Arguments can take multiple number of values. The arguments will be passed to the function as a tuple. A * must be placed before the name of parameter when defining the function.
```python
# Define gibberish
def gibberish(*args):
    """Concatenate strings in *args together."""  
    # Initialize an empty string: hodgepodge
    hodgepodge = ""      
    # Concatenate the strings in args
    for word in args:
        hodgepodge += word  
    # Return hodgepodge
    return hodgepodge  
# Call gibberish() with one string: one_word
one_word = gibberish("luke")  
# Call gibberish() with five strings: many_words
many_words = gibberish("luke", "leia", "han", "obi", "darth")  
# Print one_word and many_words
print(one_word)
print(many_words)
# luke 
# lukeleiahanobidarth
```


#### Keyword Arguments
Pass arguments as key value pairs. The parameter definition must precede with ** 
```python
# Define report_status

def report_status(**kwargs):

    """Print out the status of a movie character."""

  

    print("\nBEGIN: REPORT\n")

  

    # Iterate over the key-value pairs of kwargs

    for key, value in kwargs.items():

        # Print out the keys and values, separated by a colon ':'

        print(key + ": " + value)

  

    print("\nEND REPORT")

  

# First call to report_status()

report_status(name="luke",affiliation="jedi",status="missing")

  

# Second call to report_status()

report_status(name="anakin", affiliation="sith lord", status="deceased")
```

