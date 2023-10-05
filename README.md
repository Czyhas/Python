# Python
Password Generator

#Goal:
#1. Create a password that contain as many letters, numbers, symbols as you describe in an input function
#2. Combine them together in the random sequence

#import random
import random

#DATA
ascii_letters = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ"
digits = '0123456789'
punctuation = '!"#$%&\'()*+,-./:;<=>?@[\\]^_`{|}~'

#source: https://stackoverflow.com/questions/16060899/alphabet-range-in-python

#Convert String to List
list_letters = list(ascii_letters)
list_symbols = list(punctuation)
list_numbers = list(digits)

#source:https://www.geeksforgeeks.org/python-program-convert-string-list/

#START
print("Welcome to the PyPassword Generator!")
nr_letters=int(input("How many letters would you like in your password?\n"))
nr_symbols=int(input("How many symbols do you want in your password?\n"))
nr_numbers=int(input("How many numbers do you want in your password?\n"))

#FUNCTIONS

#INSTRUCTION

#1. Shuffle elements in each list  -> random.shuffle
#2. Describe the range of elements -> (0, nr_symbols/numbers/letters)
#3. Choose the elements from range like above
#4. Combine all lists together
#5. Shuffle the combined list
#6. Convert the list to a single elements in string

#Letter list
random.shuffle(list_letters)

for letter in list_letters:
  random_list_letters=list_letters[0:nr_letters] 

#Number list
random.shuffle(list_numbers)

for number in list_numbers:
  random_list_numbers=list_numbers[0:nr_numbers] 

#Symbol list
random.shuffle(list_symbols)

for symbol in list_symbols:
  random_list_symbols=list_symbols[0:nr_symbols]

#Combine list and shuffle
main_list=random_list_letters.copy()
main_list.extend(random_list_numbers)
main_list.extend(random_list_symbols)
random.shuffle(main_list)
print(main_list)

#Convert list to a string
password=""
for n in main_list:
    password+=n
print(password)

#Comments to output
if n >= "12" and nr_symbols >= 3 and nr_numbers >= 3:
    print("Your password is strong.")
elif n >= "8" and nr_numbers >= 2 and nr_symbols >= 1:
    print("Your password is average.")
else:
    print("Your password is weak. Please add some characters, especially numbers and symbols.")

#Options of creating passwords in secrets module

#https://docs.python.org/3/library/secrets.html#module-secrets
