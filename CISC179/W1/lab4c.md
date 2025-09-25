# 1) Unit conversion program 1a) kpl ↔ mpg

```python
# functions to convert
def kpl_to_mpg(kpl):
    return kpl * 2.3521   # formula

def mpg_to_kpl(mpg):
    return mpg * 0.4251   # formula

# ask user what they want
print("1. kpl to mpg")
print("2. mpg to kpl")
choice = input("Enter choice: ")

# if they chose kpl -> mpg
if choice == "1":
    num = input("Enter value in kpl: ")
    if num.isdigit():   # check if input is a number
        num = float(num)
        print(num, "kpl =", kpl_to_mpg(num), "mpg")
    else:
        print("Invalid input")

# if they chose mpg -> kpl
elif choice == "2":
    num = input("Enter value in mpg: ")
    if num.isdigit():
        num = float(num)
        print(num, "mpg =", mpg_to_kpl(num), "kpl")
    else:
        print("Invalid input")
else:
    print("Wrong choice")
```
# 1b)
```python
# function takes any number of arguments
def reverse_args(*args):
    # print them backwards
    for i in range(len(args)-1, -1, -1):
        print(args[i])

reverse_args(1, 2, 3, 4, 5)
```
# 1c)
```python
# changes original list
def change_list(L):
    L.append(99)

# does NOT change original list
def reassign_list(L):
    L = [1, 2, 3]

nums = [10, 20]
change_list(nums)
print("After change_list:", nums)   # [10, 20, 99]

reassign_list(nums)
print("After reassign_list:", nums) # still [10, 20, 99]
```
# 1d)
```python
x = 5

def funct_1():
    x = 3   # local x

def funct_2():
    global x
    x = 2   # changes global x

funct_1()
print("After funct_1:", x)  # 5
funct_2()
print("After funct_2:", x)  # 2
```

# 2)
```python
# use keyword arguments
def my_func(a, b, **c):
    print(c)

my_func(1, 2, x=3, y=4, z=5)
```
# 2b)
```python
def my_func_global():
    global x
    x = 100   # now this updates global x

x = 10
my_func_global()
print(x)   # prints 100
```
# Challanges
```python
# remembering when to use global
# checking if input is a number
# knowing that lists change outside a function
```
