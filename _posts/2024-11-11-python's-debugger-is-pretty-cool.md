# Python Debugger: It's Really, Really, **Really** Useful

When troubleshooting your Python code, It can be quite tedious to understand exactly what is going wrong. Error types and lines are useful, but in a large Python script, even these can be insufficient in the diagnosis of the issue. That’s where Python’s debugging mode comes in.

<br>

<img src="/blog/images/python_debugger/debugger.png" alt="Python’s Debugging mode in action">

<br>

The Python Debugger is a built-in debugging tool for Python. It provides extra functionality that running the file normally does not provide, making it easier to understand what’s going wrong with your code, especially when it comes to logical errors. Here are some examples of debugging in action:

### Example 1:
```py
#Before debugging
temperature = 75

if temperature > 80:
    print("It's hot")
elif temperature > 50:
    print("It's temperate")
elif temperature < 0:
    print("It's cold")
```

<br>

In this first example, the purpose of this code is to determine whether the temperature is hot, temperate, or cold. However, due to a logical error within the elif statements, the code does not account for numbers between 0 and 50. Using the debugging mode, we see that none of the logical statements will be fulfilled when the temperature is between 50 and 0. To fix this, we can change the final elif to an else statement, this will make sure any temperature less than 50 is classified as temperate.

<br>

```py
#After debugging
temperature = 75

if temperature > 80:
    print("It's hot")
elif temperature > 50:
    print("It's temperate")
else:
    print("It's cold")
```

<br>

### Example 2:
```py
#Before debugging
text = "Hello, world, my name is"
count = 0

for char in text:
    if char == "":
       count += 1

print(count)
```

<br>

In this example, the purpose of this code is to count the number of spaces within a string and print the result. However, using the debugger to analyze the iterations of the for loop, we see that the counter does not increase when a space is detected as intended. This is because the loop is searching for a null string (“”) rather than an empty string (“ “). To solve this we simply add a space in between the quotes on line 5, and our program works as intended.

<br>

```py
#After debugging
text = "Hello, world, my name is"
count = 0

for char in text:
    if char == " ":
       count += 1

print(count)
```

<br>

### Example 3:
```py
#Before debugging
print("give me a number")
n = input()

for num in range(1, n):
    if num % 2 < 0:
        print(num, "is even.")
    else:
        print(num, "is odd.")
```

<br>

The third example is a script that determines if the numbers between 1 and the input are even or odd. Using the debugger, were are given a TypeError on line 4. This is because the variable n is considered a string through the use of the input() function. The solution to this problem is to run the int() function outside of the input to convert whatever is input into an integer.

Next, the script will not recognize if an input is even and will default to the else statement. Although the use of modulo to detect evenness on line 5 is correct, we must compare the remainder directly to 0 rather than seeing if it is less than 0.

Finally, the loop iterates one less time than expected. This is a simple range error whose detection is made easier through the use of the debugger; the solution is to simply add 1 to the value of n after it is declared and made an integer.

<br>

```py
#After debugging
print("give me a number")
n = int(input())+1

for num in range(1, n):
    if num % 2 == 0:
        print(num, "is even.")
    else:
        print(num, "is odd.")
```

<br>

### Example 4:
```py
#Before debugging
num = int(input("Enter an integer: "))

if num < -1:
  print("No negative numbers.")
else:
  result = 1
  for i in range(1, num):
    result *= i   

  print("Factorial of " + num + "is" + result)
```

<br>

The fourth example is a factorial calculator, meant to calculate the factorial of the number inputted, “num”. However, using the debugger we notice a few issues. Specifically when the inputted number is -1, the if statement on line 3 is left unfulfilled and the script does not recognize it as negative. A simple change from -1 to 0 on that line will include -1 and all values less than it to fulfill the if statement.

A rather interesting bug can be deduced through the debugger while iterating through the for loop; The amount of iterations varies depending on the number inputted. This is because the “num” variable –used to take input and is intended to be the number we intend to get the factorial of– is used as the stop parameter of the loop. A simple solution is to change the “num” on line 7 to a constant 11 (not 10, remember, stop parameters are non-inclusive).

Even then, this script will always only present us with the factorial of 1. Right before the for loop, on line 6, the result variable will be initialized as a constant 1. What we want to do is set that variable to our “num” input, so the for loop will start with our number and give us our intended factorial.

<br>

```py
#After debugging
num = int(input("Enter an integer: "))

if num <= -1:
  print("No negative numbers.")
else:
  result = num
  for i in range(1,11):
    result *= i   

  print("Factorial of " + num + "is" + result)
```

<br>

### Example 5:
```py
#Before debugging
attempts = 0
correct_password = "secret"

while True:
    password = input("Enter your password: ")
    attempts += 1

    if password == "incorrect_password":
        print("Correct password!")
    else:
        print("Incorrect password")

    if attempts > 3:
        print("Too many attempts")
        break
```

<br>

In the final example, this simple password checker gives the user 3 attempts to input the correct password, or the script will stop executing. Firstly, the script does not seem to detect when the user enters the correct password. This is a simple fix, the script compares the input to “incorrect_password” rather than “secret”, so we can simply change the if statement on line 8 to if password == correct_password.

Now, even if the correct password is entered, and detected, the script continues to run onto other iterations. Through the debugger, I noticed that there is no difference between the result of the if and else statements of the script; both will run a new iteration of the while loop if fulfilled. To fix this, we add a break statement at the end of the if statement so that if the correct password is detected, the script will end.

Once again, we see another range issue through the final if statement (which is good because the debugger makes these very easy). The loop will only end after 4 attempts, instead of the intended 4. This is because the condition for breaking the loop on line 13 is if attempts are greater than 3 (at least 4), rather than being equal to 3.

<br>

```py
#After debugging
attempts = 0
correct_password = "secret"

while True:
    password = input("Enter your password: ")
    attempts += 1

    if password == correct_password:
        print("Correct password!")
        break
    else:
        print("Incorrect password")

    if attempts == 3:
        print("Too many attempts")
        break
```

<br>

<img src="/blog/images/python_debugger/debugger_buttons.png" alt="The many functions of debugging mode">

<br>

Ultimately, the Python debugger is an integral tool that any developer should familiarize themselves with to gain a greater understanding of their code and the logical errors one may face during their development. 