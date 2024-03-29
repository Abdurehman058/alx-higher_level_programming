0x04. Python - More Data Structures: Set, Dictionary

monoprosito
/
holbertonschool-higher_level_programming
Public
Code
Issues
Pull requests
Actions
Projects
Security
Insights
holbertonschool-higher_level_programming/0x04-python-more_data_structures/README.md
@monoprosito
monoprosito Update README.md of 'More Data Structures' project
 1 contributor
712 lines (574 sloc)  20.3 KB
More Data Structures: Set, Dictionary
Learning Objectives
What are set and how to use them
What are the most common methods of set and how to use them
When to use sets versus lists
How to iterate into a set
What are dictionary and how to use them
When to use dictionaries versus lists or sets
What is a key in a dictionary
How to iterate into a dictionary
What is a lambda function
What is map, reduce and map functions
Tasks
Squared simple
Write a function that computes the square value of all integers of a matrix.

Prototype: def square_matrix_simple(matrix=[]):
matrix is a 2 dimensional array
Returns a new matrix:
Same size as matrix
Each value should be the square of the value of the input
Initial matrix should not be modified
You are not allowed to import any module
You are allowed to use regular loops, map, etc.
Solution: 0-square_matrix_simple.py

$ amonkeyprogrammer@ubuntu:~/0x04$ cat 0-main.py
#!/usr/bin/python3
square_matrix_simple = __import__('0-square_matrix_simple').square_matrix_simple

matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

new_matrix = square_matrix_simple(matrix)
print(new_matrix)
print(matrix)

$ amonkeyprogrammer@ubuntu:~/0x04$ ./0-main.py
[[1, 4, 9], [16, 25, 36], [49, 64, 81]]
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
$ amonkeyprogrammer@ubuntu:~/0x04$ 
Search and replace
Write a function that replaces all occurrences of an element by another in a new list.

Prototype: def search_replace(my_list, search, replace):
my_list is the initial list
search is the element to replace in the list
replace is the new element
You are not allowed to import any module
Solution: 1-search_replace.py

$ amonkeyprogrammer@ubuntu:~/0x04$ cat 1-main.py
#!/usr/bin/python3
search_replace = __import__('1-search_replace').search_replace

my_list = [1, 2, 3, 4, 5, 4, 2, 1, 1, 4, 89]
new_list = search_replace(my_list, 2, 89)

print(new_list)
print(my_list)

$ amonkeyprogrammer@ubuntu:~/0x04$ ./1-main.py
[1, 89, 3, 4, 5, 4, 89, 1, 1, 4, 89]
[1, 2, 3, 4, 5, 4, 2, 1, 1, 4, 89]
$ amonkeyprogrammer@ubuntu:~/0x04$
Unique addition
Write a function that adds all unique integers in a list (only once for each integer).

Prototype: def uniq_add(my_list=[]):
You are not allowed to import any module
Solution: 2-uniq_add.py

$ amonkeyprogrammer@ubuntu:~/0x04$ cat 2-main.py
#!/usr/bin/python3
uniq_add = __import__('2-uniq_add').uniq_add

my_list = [1, 2, 3, 1, 4, 2, 5]
result = uniq_add(my_list)
print("Result: {:d}".format(result))

$ amonkeyprogrammer@ubuntu:~/0x04$ ./2-main.py
Result: 15
$ amonkeyprogrammer@ubuntu:~/0x04$
Present in both
Write a function that returns a set of common elements in two sets.

Prototype: def common_elements(set_1, set_2):
You are not allowed to import any module
Solution: 3-common_elements.py

$ amonkeyprogrammer@ubuntu:~/0x04$ cat 3-main.py
#!/usr/bin/python3
common_elements = __import__('3-common_elements').common_elements

set_1 = { "Python", "C", "Javascript" }
set_2 = { "Bash", "C", "Ruby", "Perl" }
c_set = common_elements(set_1, set_2)
print(sorted(list(c_set)))

$ amonkeyprogrammer@ubuntu:~/0x04$ ./3-main.py
['C']
$ amonkeyprogrammer@ubuntu:~/0x04$
Only differents
Write a function that returns a set of all elements present in only one set.

Prototype: def only_diff_elements(set_1, set_2):
You are not allowed to import any module
Solution: 4-only_diff_elements.py

$ amonkeyprogrammer@ubuntu:~/0x04$ cat 4-main.py
#!/usr/bin/python3
only_diff_elements = __import__('4-only_diff_elements').only_diff_elements

set_1 = { "Python", "C", "Javascript" }
set_2 = { "Bash", "C", "Ruby", "Perl" }
od_set = only_diff_elements(set_1, set_2)
print(sorted(list(od_set)))

$ amonkeyprogrammer@ubuntu:~/0x04$ ./4-main.py
['Bash', 'Javascript', 'Perl', 'Python', 'Ruby']
$ amonkeyprogrammer@ubuntu:~/0x04$
Number of keys
Write a function that returns the number of keys in a dictionary.

Prototype: def number_keys(a_dictionary):
You are not allowed to import any module
Solution: 5-number_keys.py

$ amonkeyprogrammer@ubuntu:~/0x04$ cat 5-main.py
#!/usr/bin/python3
number_keys = __import__('5-number_keys').number_keys

a_dictionary = { 'language': "C", 'number': 13, 'track': "Low level" }
nb_keys = number_keys(a_dictionary)
print("Number of keys: {:d}".format(nb_keys))

$ amonkeyprogrammer@ubuntu:~/0x04$ ./5-main.py
Number of keys: 3
$ amonkeyprogrammer@ubuntu:~/0x04$
Print sorted dictionary
Write a function that prints a dictionary by ordered keys.

Prototype: def print_sorted_dictionary(a_dictionary):
You can assume that all keys are strings
Keys should be sorted by alphabetic order
Only sort keys of the first level (don’t sort keys of a dictionary inside the main dictionary)
Dictionary values can have any type
You are not allowed to import any module
Solution: 6-print_sorted_dictionary.py

$ amonkeyprogrammer@ubuntu:~/0x04$ cat 6-main.py
#!/usr/bin/python3
print_sorted_dictionary = __import__('6-print_sorted_dictionary').print_sorted_dictionary

a_dictionary = { 'language': "C", 'Number': 89, 'track': "Low level", 'ids': [1, 2, 3] }
print_sorted_dictionary(a_dictionary)

$ amonkeyprogrammer@ubuntu:~/0x04$ ./6-main.py
Number: 89
ids: [1, 2, 3]
language: C
track: Low level
$ amonkeyprogrammer@ubuntu:~/0x04$
Update dictionary
Write a function that replaces or adds key/value in a dictionary.

Prototype: def update_dictionary(a_dictionary, key, value):
key argument will be always a string
value argument will be any type
If a key exists in the dictionary, the value will be replaced
If a key doesn’t exist in the dictionary, it will be created
You are not allowed to import any module
Solution: 7-update_dictionary.py

$ amonkeyprogrammer@ubuntu:~/0x04$ cat 7-main.py
#!/usr/bin/python3
update_dictionary = __import__('7-update_dictionary').update_dictionary
print_sorted_dictionary = __import__('6-print_sorted_dictionary').print_sorted_dictionary

a_dictionary = { 'language': "C", 'number': 89, 'track': "Low level" }
new_dict = update_dictionary(a_dictionary, 'language', "Python")
print_sorted_dictionary(new_dict)
print("--")
print_sorted_dictionary(a_dictionary)

print("--")
print("--")

new_dict = update_dictionary(a_dictionary, 'city', "San Francisco")
print_sorted_dictionary(new_dict)
print("--")
print_sorted_dictionary(a_dictionary)

$ amonkeyprogrammer@ubuntu:~/0x04$ ./7-main.py
language: Python
number: 89
track: Low level
--
language: Python
number: 89
track: Low level
--
--
city: San Francisco
language: Python
number: 89
track: Low level
--
city: San Francisco
language: Python
number: 89
track: Low level
$ amonkeyprogrammer@ubuntu:~/0x04$
Simple delete by key
Write a function that deletes a key in a dictionary.

Prototype: def simple_delete(a_dictionary, key=""):
key argument will be always a string
If a key doesn’t exist, the dictionary won’t change
You are not allowed to import any module
Solution: 8-simple_delete.py

$ amonkeyprogrammer@ubuntu:~/0x04$ cat 8-main.py
#!/usr/bin/python3
simple_delete = __import__('8-simple_delete').simple_delete
print_sorted_dictionary = \
    __import__('6-print_sorted_dictionary').print_sorted_dictionary

a_dictionary = { 'language': "C", 'Number': 89, 'track': "Low", 'ids': [1, 2, 3] }
new_dict = simple_delete(a_dictionary, 'track')
print_sorted_dictionary(a_dictionary)
print("--")
print_sorted_dictionary(new_dict)

print("--")
print("--")
new_dict = simple_delete(a_dictionary, 'c_is_fun')
print_sorted_dictionary(a_dictionary)
print("--")
print_sorted_dictionary(new_dict)

$ amonkeyprogrammer@ubuntu:~/0x04$ ./8-main.py
Number: 89
ids: [1, 2, 3]
language: C
--
Number: 89
ids: [1, 2, 3]
language: C
--
--
Number: 89
ids: [1, 2, 3]
language: C
--
Number: 89
ids: [1, 2, 3]
language: C
$ amonkeyprogrammer@ubuntu:~/0x04$
