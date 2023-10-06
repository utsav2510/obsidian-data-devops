A good practice in writing your own [[Python/Functions]] is also anticipating the ways in which other people  might use the function you defined.
Eg: the `len()` function is able to handle input arguments such as strings, lists, and tuples, but not int type ones and raises an appropriate error and error message when it encounters invalid input arguments. One way of doing this is through exception handling with the `try-except` block.

```python
# Define shout_echo

def shout_echo(word1, echo=1):

    """Concatenate echo copies of word1 and three

    exclamation marks at the end of the string."""

  

    # Initialize empty strings: echo_word, shout_words

    echo_word = ""

    shout_words = ""

    # Add exception handling with try-except

    try:

        # Concatenate echo copies of word1 using *: echo_word

        echo_word = word1 * echo

  

        # Concatenate '!!!' to echo_word: shout_words

        shout_words = echo_word + '!!!'

    except:

        # Print error message

        print("word1 must be a string and echo must be an integer.")

  

    # Return shout_words

    return shout_words

  

# Call shout_echo

shout_echo("particle", echo="accelerator")
```

Another way to **raise** an error is by using `raise`

```python
# Define shout_echo

def shout_echo(word1, echo=1):

    """Concatenate echo copies of word1 and three

    exclamation marks at the end of the string."""

  

    # Raise an error with raise

    if echo < 1:

        raise ValueError('echo must be greater than or equal to 0')

  

    # Concatenate echo copies of word1 using *: echo_word

    echo_word = word1 * echo

  

    # Concatenate '!!!' to echo_word: shout_word

    shout_word = echo_word + '!!!'

  

    # Return shout_word

    return shout_word

  

# Call shout_echo

shout_echo("particle", echo=5)
```