# 1 a)
kg = input("Enter weight in kilograms: ")
kg = float(kg)
pounds = kg * 2.2
print(pounds)

# b)
netBalance = float(input("Enter net balance: "))
payment = float(input("Enter payment: "))
d1 = int(input("Enter number of days in billing cycle: "))
d2 = int(input("Enter number of days before billing cycle: "))
rate = float(input("Enter monthly interest rate: "))

averageDailyBalance = (netBalance * d1 - payment * d2) / d1
interest = averageDailyBalance * rate
print(interest)

# c) 
x = float(input("Enter speed of car A: "))
y = float(input("Enter speed of car B: "))
time = float(input("Enter time in hours: "))

distanceA = x * time
distanceB = y * time
distance = (distanceA ** 2 + distanceB ** 2) ** 0.5
print(distance)

# 2 
a. hello = "hello"
# works fine
b. _var = 100
# works fine
c. !var_1 = 200
# does not work because variable names can't start with symbols the correct way would be --> var_1 = 200 
d. print = "print me" 
# works fine but i dont recommend it because you can no longer use the print() function anymore
e. False = 0
# doesnt work bc False is a set word that you cannot change in python
