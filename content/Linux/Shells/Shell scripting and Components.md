**Scripting**
Shell script is a set of commands.
All the shells have ability to do this.
Scripting can be done in various languages.
Need to create a file for the script using a text editor.
	The file has to be named with the *.sh* extension
Every script should start with shebang.
	Shebang is a combination of some characters that are added at the beginning of a script, starting with *#!* followed by the name of the interpreter to use while the script executes. (at the top of the script)

**Variables** - Store a value inside.
	*echo* - prints the text in speech marks "here"
	*read* - take input from the user
```shell
# Defining the Interpreter 
#!/bin/bash
echo "Hey, what’s your name?"
read name
echo "Welcome, $name"
```

**Loops** - repeat commands
	*do* - start of the loop
	*done* - end of the loop
```shell
# Defining the Interpreter 
#!/bin/bash
for i in {1..10};
do
echo $i
done
```

**Conditional Statements** - execute specifics only when a condition is met.
	*if* - starts the condition
	*fi* - ends the condition
```shell
# Defining the Interpreter 
#!/bin/bash
echo "Please enter your name first:"
read name
if [ "$name" = "Stewart" ]; then
        echo "Welcome Stewart! Here is the secret: THM_Script"
else
        echo "Sorry! You are not authorized to access the secret."
fi
```

**Comments** - used to add text comments to parts of code. Is not executed.
	*#* - Hash, followed by a space.   

Script to utilise them all:
```shell
# Defining the Interpreter 
#!/bin/bash 

# Defining the variables
username=""
companyname=""
pin=""

# Defining the loop
for i in {1..3}; do
# Defining the conditional statements
        if [ "$i" -eq 1 ]; then
                echo "Enter your Username:"
                read username
        elif [ "$i" -eq 2 ]; then
                echo "Enter your Company name:"
                read companyname
        else
                echo "Enter your PIN:"
                read pin
        fi
done

# Checking if the user entered the correct details
if [ "$username" = "John" ] && [ "$companyname" = "Tryhackme" ] && [ "$pin" = "7385" ]; then
        echo "Authentication Successful. You can now access your locker, John."
else
        echo "Authentication Denied!!"
fi
```

