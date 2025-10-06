```python
# Lab 6: Text Parsing
# Author: Gavin 
# This program counts words and characters in a story,
# finds emails and phone numbers using regex,
# and makes new emails ending with @hotmail.com.
```
## [![Watch the video](https://img.youtube.com/vi/3cytcu-i7Rg/0.jpg)](https://youtu.be/3cytcu-i7Rg)
```python

import re  # used to find patterns like emails or phone numbers

# === STORY TEXT ===
# Replace this with the story your teacher gave you
story = """
Contact us at Support.Team@example.com or call (415) 555-2671.
You can also reach me at personal_email123@test.org or +1 415 555 2672.
This story shows how to count words and characters and find patterns in text.
The cat and the dog ran and ran; and the cat won.
"""

# === STEP 1: Using a list ===
# Split the story into individual words
words = story.split()

# Count how many words and characters there are
word_count = len(words)
char_count = len(story)

print("=== Step 1: Using a List ===")
print("Total words:", word_count)
print("Total characters:", char_count)

# Make a list of unique words (no repeats)
unique_words = []
for w in words:
    w_clean = w.lower().strip(",.;!?")  # make lowercase and remove punctuation
    if w_clean not in unique_words:
        unique_words.append(w_clean)

# Print how many times each word appears
print("\nUnique words and how many times they appear:")
for w in unique_words:
    print(w, ":", words.count(w))

# === STEP 2: Using a dictionary ===
# A dictionary stores word: count pairs
print("\n=== Step 2: Using a Dictionary ===")
word_freq = {}

for w in words:
    w_clean = w.lower().strip(",.;!?")
    if w_clean in word_freq:
        word_freq[w_clean] += 1  # if word already in dictionary, add 1
    else:
        word_freq[w_clean] = 1  # if new word, set count to 1

# Print each word and its count
for word, count in word_freq.items():
    print(word, ":", count)

# === STEP 3: Regular expressions for data extraction ===
print("\n=== Step 3: Regex Extraction ===")

# Find all emails in the text
emails = re.findall(r"[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}", story)

# Find all phone numbers in the text
phones = re.findall(r"\+?\d[\d\s\-\(\)]{8,}\d", story)

print("Emails found:", emails)
print("Phones found:", phones)

# Combine both emails and phones into one list
contacts = emails + phones
print("All contacts in one list:", contacts)

# === STEP 4: Email username processing ===
print("\n=== Step 4: Email Username -> Hotmail ===")

# Make a new list with the usernames changed to @hotmail.com
hotmail_list = []
for email in emails:
    username = email.split("@")[0]  # take everything before @
    new_email = username + "@hotmail.com"
    hotmail_list.append(new_email)

print("Converted emails:", hotmail_list)

print("\nDone ✅  Replace the story text above with your real one before submitting!")
```
