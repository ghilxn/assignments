```python
1) Creating and accessing dictionary
 Make any dictionary with 10 elements
# 1a
school = {
    "id": 1001,
    "name": "Alex",
    "age": 18,
    "major": "CS",
    "gpa": 3.4,
    "city": "San Diego",
    "state": "CA",
    "units": 15,
    "enrolled": True,
    "grad_year": 2028
}
print("len:", len(school))
print(school)

```


```python
# 1b
my_user_dict = {}

# required fields from example
ssn = input("SSN: ")
name = input("Name: ")
my_user_dict["SSN"] = ssn
my_user_dict["Name"] = name

```

```python
# optional extra key/value pairs
while True:
    cont = input("Do you want to add another key/value? (Y/N): ").strip().upper()
    if cont == "Y":
        k = input("Key: ")
        v = input("Value: ")
        # if key already exists, simple overwrite or let the user change it
        if k in my_user_dict:
            print("That key already exists. Choose a different key.")
            k = input("New Key: ")
        my_user_dict[k] = v
    else:
        break

print("my_user_dict:", my_user_dict)

```

```python
# example given
a = [("a", 1), ("b", 2), ("c", 3)]
res = dict(a)
print(res)  # {'a': 1, 'b': 2, 'c': 3}

```

```python
#1c data = [
    ('Name', 'Sarah Connor'),
    ('Date of birth', '1 Jan 1980'),
    ('Address', '1000 Black Mountain Drive', 92126),  # <- has 3 items (not a key,value pair)
    ('Name', 'Jim Hawkins')                            # <- duplicate key
]

fixed = {}
i = 0
while i < len(data):
    item = data[i]
```
```python
    # check arity (must be 2)
    if len(item) != 2:
        print("Found invalid pair at index", i, "->", item)
        print("Please enter a single VALUE to use for this key:", item[0])
        user_value = input("Value for key '" + str(item[0]) + "': ")
        key = item[0]
        # check duplicate key
        if key in fixed:
            print("Duplicate key detected:", key)
            key = input("Enter a different key name: ")
        fixed[key] = user_value

    else:
        key = item[0]
        value = item[1]
        # check duplicate key
        if key in fixed:
            print("Duplicate key detected:", key)
            key = input("Enter a different key name: ")
        fixed[key] = value

    i += 1

print("Validated dict:", fixed)

```

```python
# 1d
pairs_list = [["k1", 10], ["k2", 20], ["k3", 30], ["k4", 40]]
out = {}
idx = 0
while idx < len(pairs_list):
    pair = pairs_list[idx]
    # assume each sub-item is [key, value]
    if len(pair) == 2:
        out[pair[0]] = pair[1]
    else:
        # if it isn't exactly 2, just skip or ask the user (keeping it simple here)
        pass
    idx += 1

print("Converted dict:", out)

```

```python
# 1e
text = ("The tiger (Panthera tigris) is a large cat and a member of the genus Panthera native to Asia. "
        "It has a powerful, muscular body with a large head and paws, a long tail and orange fur with black, mostly vertical stripes. "
        "It is traditionally classified into nine recent subspecies, though some recognise only two subspecies, mainland Asian tigers and the island tigers of the Sunda Islands.")

# split on spaces; keep punctuation in words (simple approach, case-sensitive)
words = text.split()

counts = {}
i = 0
while i < len(words):
    w = words[i]
    if w in counts:
        counts[w] += 1
    else:
        counts[w] = 1
    i += 1

```

```python
# show a few sample counts to keep output shorter
print("Count('The'):", counts.get("The", 0))
print("Count('the'):", counts.get("the", 0))
print("Unique word count:", len(counts))
# If you want to see all, uncomment:
# print(counts)

d_orig = {123: "Coconut"}
d_copy = d_orig
print(d_orig)
print(d_copy)

```
```python
# 2a
d_orig = {123: "Coconut"}
d_copy = d_orig.copy()  # make a separate copy first
d_copy[456] = "Mango"

print("d_orig:", d_orig)  # stays {'123': 'Coconut'}
print("d_copy:", d_copy)  # has the extra key

```

```python
# 2b
# Problem: using d_copy = d_orig makes both names point to the same dict (aliasing).
# Solution: make a copy before editing.
d_orig = {"a": 1, "b": {"nested": True}}
# shallow copy is fine for flat dicts:
d_copy_shallow = d_orig.copy()
# deep copy for nested structures:
import copy
d_copy_deep = copy.deepcopy(d_orig)

# show that editing the deep copy doesn't affect original nested stuff
d_copy_deep["b"]["nested"] = False
print("original:", d_orig)
print("deepcopy:", d_copy_deep)

```

```python
# 2c
# This line causes the error below if you run it.
# d_bad = { [1, 2]: "nope" }   # TypeError: unhashable type: 'list'

# To keep this file runnable, leaving it commented out.
# Safe alternative:
d_ok = { (1, 2): "works (tuple key)" }
print(d_ok)

```
```python
# remembering keys must be unique; handled duplicates by asking the user to rename

# no try/except, so I used simple if/else checks and while loops

# word count is case-sensitive on purpose (so “The” and “the” are different)
```
