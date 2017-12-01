#!/usr/bin/env python3
# -*- coding: utf-8 -*-
"""
Created on Fri Dec  1 10:59:21 2017

@author: liat
"""

# Creating an interactive dictionary
# Using a JSON file containing a real dictionary
'''Dictionary can identify word that are of a close match to the real 
word, for instance, rainn instead of rain would be identified.'''
'''First conditional statement checks whether the data exists in the dictionary. If not, 
it will return "The word doesn't exist. Please double check it.'''

'''lower - converts the statement to a lower case'''

import json
from difflib import get_close_matches

data = json.load(open("data.json"))

def translate(w):
    w = w.lower()
    if w in data:
        return data[w]
    elif len(get_close_matches(w, data.keys())) > 0:
        yn = input("Did you mean %s instead? Enter Y if yes, or N if no: " % get_close_matches(w, data.keys())[0])
        if yn == "Y":
            return data[get_close_matches(w, data.keys())[0]]
        elif yn == "N":
            return "The word doesn't exist. Please double check it."
        else:
            return "We didn't understand your entry."
    else:
        return "The word doesn't exist. Please double check it."

word = input("Enter word: ")
output = translate(word)
if type(output) == list:
    for item in output:
        print(item)
else:
    print(output)
