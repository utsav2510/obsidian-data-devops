Some [[Python/Functions]] definitions are simple enough that they can be converted to a lambda function. By doing this, you write less lines of code.
```python
# Define echo_word as a lambda function: echo_word
echo_word = (lambda word1,echo: word1 * echo)
# Call echo_word: result
result = echo_word('hey',5)
# Print result
print(result)
```

#### Map Function
The best use case for lambda functions, however, are for when you want these simple functionalities to be anonymously embedded within larger expressions. What that means is that the functionality is not stored in the environment, unlike a function defined with `def`. To understand this idea better, you will use a lambda function in the context of the `map()` function.

 `map()` applies a function over an object, such as a list. Here, you can use lambda functions to define the function that `map()` will use to process the object. For example:

```python
nums = [2, 4, 6, 8, 10]

result = map(lambda a: a ** 2, nums)
```

You can see here that a lambda function, which raises a value `a` to the power of 2, is passed to `map()` alongside a list of numbers, `nums`. The _map object_ that results from the call to `map()` is stored in `result`. You will now practice the use of lambda functions with `map()`. For this exercise, you will map the functionality of the `add_bangs()` function you defined in previous exercises over a list of strings.

```python
# Create a list of strings: spells
spells = ["protego", "accio", "expecto patronum", "legilimens"]
# Use map() to apply a lambda function over spells: shout_spells
shout_spells = map(lambda item: item + '!!!', spells)
# Convert shout_spells to a list: shout_spells_list
shout_spells_list = list(shout_spells)
# Print the result
print(shout_spells_list)
```

#### Filter Function
Used to filter out the values which don't meet a condition.

```python
# Create a list of strings: fellowship
fellowship = ['frodo', 'samwise', 'merry', 'pippin', 'aragorn', 'boromir', 'legolas', 'gimli', 'gandalf']
# Use filter() to apply a lambda function over fellowship: result
result = filter(lambda member: len(member) > 6, fellowship)
# Convert result to a list: result_list
result_list = list(result)
# Print result_list
print(result_list)

# ['samwise', 'aragorn', 'boromir', 'legolas', 'gandalf']
```

#### Reduce Function
The `reduce()` function is useful for performing some computation on a list and, unlike `map()` and `filter()`, returns a single value as a result. To use `reduce()`, you must import it from the `functools` module.

```python
# Import reduce from functools
from functools import reduce
# Create a list of strings: stark
stark = ['robb', 'sansa', 'arya', 'brandon', 'rickon']
# Use reduce() to apply a lambda function over stark: result
result = reduce(lambda item1,item2: item1 + item2, stark)
# Print the result
print(result)
```
