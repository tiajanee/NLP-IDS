NLTK BOOK CHAPTER ONE RESOURCE

#### Given an alphabet of 26 letters, there are 26 to the power 10, or 26 ** 10, ten-letter strings we can form. That works out to 141167095653376. How many hundred-letter strings are possible?
(26^100) strings

#### The Python multiplication operation can be applied to lists. What happens when you type ['Monty', 'Python'] * 20, or 3 * sent1?

20 lists

#### Review 1 on computing with language. How many words are there in text2? How many distinct words are there?
141576
6833

####Compare the lexical diversity scores for humor and romance fiction in 1.1. Which genre is more lexically diverse?

humor

#### Find the collocations in text5.

wanna chat; PART JOIN; MODE #14-19teens; JOIN PART; PART PART;
cute.-ass MP3; MP3 player; JOIN JOIN; times .. .; ACTION watches; guys
wanna; song lasts; last night; ACTION sits; -...)...- S.M.R.; Lime
Player; Player 12%; dont know; lez gurls; long time

#### Consider the following Python expression: len(set(text4)). State the purpose of this expression. Describe the two steps involved in performing this computation.

First we use the set method to get all of the unique words (no repeats) and then we get the length of the set to see how many unique words we have

#### Try adding the string to itself using my_string + my_string, or multiplying it by a number, e.g., my_string * 3. Notice that the strings are joined together without any spaces. How could you fix this?
(my_string + " ") * 3


### Consider the following two expressions, which have the same value. Which one will typically be more relevant in NLP? Why?

```python
"Monty Python"[6:12]
["Monty", "Python"][1]
```
The second. Often we won't know the length of the word we are looking for, but we don't need the length to get to access the second word in a list. We just need the index, which is always 1.

#### We have seen how to represent a sentence as a list of words, where each word is a sequence of characters. What does sent1[2][2] do? Why? Experiment with other index values.

returns the third character of the third word in list sent1.


#### Review the discussion of conditionals in 4. Find all words in the Chat Corpus (text5) starting with the letter b. Show them in alphabetical order.

```python
words=[]
for word in text5:
    if word[0] == "b":
    	words.append(word)
sorted(words)
set(words)
```


#### Using list addition, and the set and sorted operations, compute the vocabulary of the sentences sent1 ... sent8.

set(sorted(sent1+sent8))

#### What is the difference between the following two lines? Which one will give a larger value? Will this be the case for other texts?

```python
sorted(set(w.lower() for w in text1))
sorted(w.lower() for w in set(text1))
```

The latter will give larger value. Calling the lower method before the set method ensure we do not deem "the" and "The" as different words.
Since if the second line, the lower method is called after the set, we have the chance of returning duplicates.

#### Write the slice expression that extracts the last two words of text2.
text2[:-2]

#### Find all the four-letter words in the Chat Corpus (text5). With the help of a frequency distribution (FreqDist), show these words in decreasing order of frequency.

```python
words = []
for word in text5:
    if len(word) == 4:
    	words.append(word)
FreqDist(words)
```

#◑ Review the discussion of looping with conditions in 4. Use a combination of for and if statements to loop over the words of the movie script for Monty Python and the Holy Grail (text6) and print all the uppercase words, one per line.

```python
for word in text6:
	if word.isupper():
 		print(word)
```


####Define sent to be the list of words ['she', 'sells', 'sea', 'shells', 'by', 'the', 'sea', 'shore']. Now write code to perform the following tasks:
#####Print all words beginning with sh
#####Print all words longer than four characters

```python
sent = ['she', 'sells', 'sea', 'shells', 'by', 'the', 'sea', 'shore']

for word in sent:
	if len(word) > 4:
		print(word)

for word in sent:
	if word.startswith("sh"):
		print(word)

```
#### What does the following Python code do?  sum(len(w) for w in text1) Can you use it to work out the average word length of a text?

Adds the length of word in the text together to one value, if you count the number of words in the text and divide the sum by the count you could get the average word length

#### Define a function called vocab_size(text) that has a single parameter for the text, and which returns the vocabulary size of the text.

```python
def vocab_size(text):
    return len(set(text))
```
#### Define a function percent(word, text) that calculates how often a given word occurs in a text, and expresses the result as a percentage.
        
```python
        def percent(word, text):
     		word_count = text.count(word)
     		per = ((word_count / len(text)) * 100)
     		print(per)
```

