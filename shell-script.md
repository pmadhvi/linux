#! /bin/bash

## Echo command:
`Echo used for returning/printing the information on stdout.`
echo Hello World!

## Variables:
`Varibales used for holding an value in memory. Should be Uppercase by convention. Any Letters, Numbers and underscores can be used. For accessing the varibales, always use '$' or '${VAR-NAME}' in front of variable name.`

NAME="Bobby"
echo "My name is $NAME."
echo "My name is ${NAME}."

## User Input:
`read command is used for taking the input from stdin.
-p is used for prompting the text to the stdout.
NAME is used as varibale for captuirng the user entered data.`

read -p "Enter your name:" NAME
echo "Your name is ${NAME}."

`Incase you do not want to prompt any text at stdout then use following: Here read will read the user provided input and store it in variable NAME.`

read NAME
echo "Your name is ${NAME}."

## IF statement:
`if condition then result and fi`

if [ "$NAME" ==  "Thomas" ]
then 
    echo "Your name is Thomas"
fi

## IF-ELSE statement:
if [ "$NAME" ==  "Thomas" ]
then 
    echo "Your name is Thomas"
else
    echo "Your name is something else"
fi

## IF-ELSE-IF-ELSE statement:

if [ "$NAME" ==  "Thomas" ]
then 
    echo "your name is Thomas"
elif  [ "$NAME" ==  "Fred" ]
then 
     echo "your name is Fred"
else
     echo "your name is not Thomas nor Fred"
fi

## COMPARISON
NUM1=40
NUM2=35

if [ "$NUM1"  -gt  "$NUM2" ]
then
    echo "$NUM1 is greater than $NUM2."
else
    echo "$NUM2 is greater than $NUM1."
fi

### Different comparison operators:

* val1 -eq val2 => Returns true if the values are equal

* val1 -ne val2 => Returns true if the values are not equal

* val1 -gt val2 => Returns true if val1 is greater than val2

* val1 -ge val2 => Returns true if val1 is greater than or equal to val2

* val1 -lt val2 => Returns true if val1 is less than  val2

* val1 -le val2 => Returns true if val1 is less than or   equal to val2

## CASE STATEMENT:
read -p "Is your age above 18? Y/N" ANSWER
case "$ANSWER" in
    [yY]|[yY][eE][sS])
        echo "You are allowed to have drinks"
        ;;
    [nN]|[nN][oO])
        echo "You can enjoy juices"
        ;;
    *)
        echo "Enter your age"
        ;;
esac

## FILE CONDITIONS:
FILE="file.txt"
if [ -e "$FILE" ]
then 
    echo "$FILE exists"
else 
    echo "$FILE does not exists"
fi

### Different file operators:
* -d file => True if file is an directory
* -e file => True if file exists
* -f file => True if provided string is file
* -g file => True if the group id is set on file
* -r file => True if file is readable
* -s file => True if file has non zero size
* -u file => True if the user id is set on a file
* -w file => True if file is writtable
* -x file => True is file is an executable

## FOR LOOP:
NAMES="Brad Kevin Alice Mark"
for NAME in $NAMES
  do 
    echo "Hello $NAME"
done

## WHILE LOOP:
LINE=1
WHILE read -r CURRENT_LINE
  do 
    echo "$LINE: $CURRENT_LINE"
    ((LINE++))
done < "./shell-script.sh"

## FUNCTION:
function helloWorld(){
    echo "Hello World"
}
helloWorld 
`helloWorld will call the function. `

## FUNCTION WITH PARAMS:
function intro(){
    echo "Hello I am $1 and I am $2 years old"
}
intro "Brad" "36"
`intro Brad will call the function with param Brad. You can pass in multiple params and access them using numbers $1, $2 and so on. `

## CREATE FOLDER AND WRITE TO A FILE
mkdir hello
touch hello/world.txt
echo "Hello World" >> hello/world.txt
echo "created hello/world.txt"