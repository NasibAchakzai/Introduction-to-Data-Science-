# Introduction-to-Data-Science-
Introduction to Data Science 
Data Science is a combination of multiple disciplines that uses statistics, data analysis, and machine learning to analyze data and to extract knowledge and insights from it.
Python Basic Syntax 
## Python Basic Syntax
This is a basic Python program that uses the print() function to output the message "Hello, world!" to the console. It's often used as a simple starting point when learning a new programming language.
#
print("Naeesb Ullah!")
## Variables and data types
This code demonstrates how to define variables in Python and assign them different data types. The name variable is a string, the age variable is an integer, the is_male variable is a boolean, and the height variable is a float.
#
This code defines two variables A and B with values 2 and 3 respectively. Then, it performs an addition operation using the + operator on these two variables and prints the result of the addition operation to the console. In this case, the result of the addition operation is 8, so the output of the code will be 5

 A=2 
B=3
 print(A+B) = 5
 ## Functions
Functions in Python are a way to group a set of related statements together that perform a specific task. Functions make the code more modular, easier to read, and reusable.

In Python, you can define a function using the def keyword followed by the function name and the parameters (if any) in parentheses. The function body is indented after a colon and contains the code that is executed when the function is called.

Here is an example of a simple function that takes two parameters x and y, adds them 
#
def add(x, y):
    result = x + y
    return result
sum = add(2, 3)
print(sum)  
# 
Output: 5
## There are several data types
Numeric types: integers, floating-point numbers, and complex numbers.
Integers are whole numbers (positive, negative, or zero) without a decimal point, such as 42 or -10.
Floating-point numbers (also called floats) are decimal numbers, such as 3.14 or -0.5.
Complex numbers are represented as a sum of a real number and an imaginary number, such as 1 + 2j.
Boolean type: This type represents the truth values True and False.

Sequence types: These are ordered collections of elements:

Lists: mutable ordered sequence of elements enclosed in square brackets [].
Tuples: immutable ordered sequence of elements enclosed in parenthesis ().
Range: immutable sequence of numbers, used to generate a sequence of numbers.
Strings: immutable sequence of characters, enclosed in either single or double quotes.
Mapping types: These are collections of key-value pairs:
Dictionaries: mutable key-value mapping enclosed in curly braces {}.
Set types: These are collections of unique elements:
Sets: mutable unordered collection of unique elements enclosed in curly braces {}.
data types include:
 #### Numeric types:
x = 42        # int
y = 3.14      # float
z = 1 + 2j    # complex

#### Boolean type:
is_true = True
is_false = False

#### List type
my_list = [1, 2, 3, 'four', 5.0]

#### Tuple type
my_tuple = (1, 2, 3, 'four', 5.0)

#### Dictionary type
my_dict = {'name': 'John', 'age': 30, 'city': 'New York'}

#### Set type
my_set = {1, 2, 3, 4, 5}
Python also provides a variety of built-in functions and methods for working with these data types, such as len(), append(), remove(), and many more.






bool (True or False)
Sequence types:

list (mutable ordered sequence of elements)
tuple (immutable ordered sequence of elements)
range (immutable sequence of numbers)
str (immutable sequence of characters)
bytes (immutable sequence of bytes)
bytearray (mutable sequence of bytes)
Mapping types:

dict (mutable key-value mapping)
Set types:

set (mutable unordered collection of unique elements)
## conditional statements
 conditional statements allow you to execute different blocks of code depending on whether a certain condition is true or false. The most common conditional statements in Python are if, elif, and else.
 ####
a=8

if(a %2 ==0):
    print("this even number")
else:
        print("this Odd number")
## loop
loop is used to iterate over a sequence or other iterable object and execute a block of code for each item in the sequence. The basic syntax of a for loop in Python is as follows:
#
numbers = [1, 2, 3, 4, 5]

for num in numbers:
    print(num)
  ## CSV files
   you can work with CSV (Comma Separated Values) files using the csv module. This module provides functionality to read and write CSV files in various formats including comma-separated values, tab-separated values, and other delimiter-separated values.

To read a CSV file in Python, you can use the csv.reader() function. This function takes a file object as input and returns a reader object which can be used to iterate over the rows in the CSV file. Here's an example:
####
import csv

with open('example.csv', 'r') as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)

    
