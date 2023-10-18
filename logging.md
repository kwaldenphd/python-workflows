# Other Debugging Approaches

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>This tutorial was written by Katherine Walden and is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

# Overview

If you've never put a `print()` statement in your code to output a variable's value while the program is running, you have used a form of `logging` to debug your code. Python's `logging` module lets you record custom messages that output as part of your program. These `log` messages describe when the program reaches a point where a logging function is called and what variables have been specified at that point.

Step one is to import the `logging` module and set up basic configuration for the module at the top of your `.py` file.
```Python
import logging
logging.basicConfig(level=logging.DEBUG, format=' %(asctime)s - %(levelname)s - %(message)s')
```

This configuration information instructs Python to create a `LogRecord` object when a logging function is called, and to include specific information about that event in the `LogRecord` object.

So how would we use the `logging` module when writing a program? Say we were creating a function that calcualted the factorial of a given number.
- Factorial 4 is 1 x 2 x 3 x 4 = 24
- Factorial 7 is 1 x 2 x 3 x 4 x 5 x 6 x 7 = 5040

```Python
import logging
logging.basicConfig(level=logging.DEBUG, format=' %(asctime)s - %(levelname)s - %(message)s')
logging.debug('Start of program')

def factorial(n):
  logging.debug('Start of factorial(%s%%)' % (n))
  total = 1
  for i in range(n + 1):
    total *= i
    logging.debug('i is ' + str(i) + ', total is ' + str(total))
  logging.debug('End of factorial(%s%%)' % (n))
  return total

print(factorial(5))
logging.debug('End of program')
```

Anytime we call the `logging.debug()` function, the configuration information from the start of the file governs the log formatting and messages.

<blockquote>Q5: What happens when we run this program? What kinds of log messages do we get, and what information do they give us?</blockquote>

<blockquote>Q6: Is this program doing what we expect? Where would you go next with debugging or addressing the error?</blockquote>

### But why can't I debug using `print()`

It can seem unwieldy to configure the `logging` module and write lines of code dedicated just to logging what's happening in your program. But think about the factorial example. Log messages led us right to the program's issue. Trying to debug using `print()` calls means you'll have to go back through each line of your program to remove `print()` statements used for debugging (while also making sure you aren't removing `print()` statements that are a component of the actual program).

Think of the `logging` module as a report that generates alongside your program output as it executes. The program executes and you also have useful log information about what happened along the way. Once you're done debugging the program, you can add the `logging.disable()` function to the start of your program to supress the log messages without actually having to modify your program.

<blockquote>Visit Python's <a href="https://docs.python.org/3/howto/logging.html">Logging HOWTO</a> documentation to learn more about the logging module.</blockquote>
