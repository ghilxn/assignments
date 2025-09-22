# 1a
a = input("Enter first: ")
b = input("Enter second: ")
c = input("Enter third: ")
d = input("Enter fourth: ")
e = input("Enter fifth: ")

my_tuple = (a, b, c, d, e)
print(my_tuple)

You can’t. Tuples can’t be changed after they are made.
If you need to “change” one, you gotta make a new tuple.

# 1c
my_tuple = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)

print("Count of 1:", my_tuple.count(1))
print("Count of 2:", my_tuple.count(2))
print("Count of 3:", my_tuple.count(3))
print("Count of 4:", my_tuple.count(4))
print("Count of 5:", my_tuple.count(5))

# 1d
my_tuple = (1,2,3)
print("Before:", my_tuple, "id:", id(my_tuple))

my_tuple = my_tuple + my_tuple
print("After: ", my_tuple, "id:", id(my_tuple))

#1e) x = (1,2,3,4)

x.append(1)      # error, no append in tuple
x[1] = "hello"   # error, can’t change an item
del x[2]         # error, can’t delete from tuple

(one, two, three, four) = (1,2,3,4)

#2a) Data types

All four are int.

#2b) Example with *
x = (1,2,3,4)
a, b, *c = x
print(a, b, c)   # 1 2 [3, 4]

#2c) a, *b, c = x
x = (1,2,3,4)
a, *b, c = x
print(a)   # 1
print(b)   # [2, 3]
print(c)   # 4

#3. Memory management
my_x = [100,200,300,400]
my_y = (200,300,400,500)

print("List id:", id(my_x))
print("Tuple id:", id(my_y))

print("List element ids:", [id(i) for i in my_x])
print("Tuple element ids:", [id(i) for i in my_y])
