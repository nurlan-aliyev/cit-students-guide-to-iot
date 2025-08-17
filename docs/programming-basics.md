# Programming Basics

## Structure
The basic structure of the Arduino programming language is very simple and consists of at least two parts. These two parts are the functions required for the program to work. And functions consist of various commands.

```c title="basic_arduino_sketch.ino" linenums="1"
 void setup()
{
    //This runs once;
}

void loop()
{
    //This runs until interrupted;
}
```
   

Here `setup()` is a program preparation, and `loop()` is a function that executes commands. Both functions must be specified when writing the program.

At the beginning of the program, the variables to be used must be specified within the `setup()` function. The setup function is the initial function of the program and is called only once during the execution of the program and can be used either for the `pinMode()` (more information on the following topics) or to create a serial connection between the Arduino board and the computer.

The loop function is called after the setup and constantly reads commands - input data, output signal, etc. executes. From this we can say that the loop function is the basis of all Arduino programs, and most of the executed program falls on it.


### setup()
The `setup()` function is called only once during program execution, and can be used to assign pins on a board or to establish a serial connection. Even if there is no executable code block, the program must write the `setup()` function. 

```c linenums="1"
void setup()
{
    pinMode(pin, OUTPUT); //sets pin as OUTPUT
}
```

### loop()
After the `setup()` function is called, the `loop()` function, as the name implies, loops sequentually to control the Arduino board, respond to external signals, etc. In short, the loop function is the basis of the Arduino program.

```c linenums="1"
void loop()
{
    digitalWrite(pin, HIGH); //turns pin on
    delay(1000);             //pauses for 1 sec.
    digitalWrite(pin, LOW);  //turns pin off
    delay(1000);             //pauses for 1 sec.
}
```

### Functions
A function is a block of code with its own name and commands inside. These commands are executed when the function is called.
There is enough information about the `setup()` and `loop()` functions, and we will talk about other pre-written functions in the following topics. 

You can create functions yourself to solve any problem you want and eliminate confusion that may arise in the program. To do this, you must first determine the **type** of function. The output results of the functions correspond to the defined types, e.g. The result of a function of type **integer** will also be an integer. If no output is expected from the function, then the type of such function should be written as **void**.

```c linenums="1"
type functionName(parameters)
{
    commands;
}
```

The `delayVal()` function of the integer type shown below is designed to pause a program using a value read from a potentiometer. Initially, it defines the variable **"v"** within the function, equates the value of that variable to a value between 0-255 read from the potentiometer, and finally returns the value of the variable v as a result. 

```c linenums="1"
int delayVal()
{
    int v;               //temporary v variable
    v = analogRead(pot); //read pot. value
    v /= 4;              //converse 0-1023 to 0-255
    return v;            //return final value
}
```

### {}Curly braces
Curly brackets define the beginning and end of function and condition blocks. 

```c linenums="1"
type function()
{
    commands;
}
```

The open curly bracket must be closed. If left unchecked, this can lead to compilation errors that are difficult to find in the program. The best way to prevent this is to close the bracket as soon as you open it and write down the commands inside. 

There is a convenient way to check this balance in an Arduino environment. Just select the open bracket, and the other half of it will be highlighted.

### ;Semicolon
A semicolon is used to terminate any command, or to separate elements of a program. It is also used to separate commands in parentheses during `for` loop in which it's mandatory. 

```c linenums="1"
int x = 13; //x is equal to 13
```

!!! note 
    If a semicolon is not placed in the required place on any line, a compilation error may occur again, so it is better to put it on the place where the semicolon should be placed before writing the command. 

### /*...*/Comments 
A comment block is a field of text used to provide general information about a program or any operation to users. The program does not read the comment block and does not execute any line. These blocks start with `/*` and end with `*/`.

```c linenums="1"
/* Do not forget
    to close the comment block!
*/
```

### //Line comments
Single line comments start with `//` and convert the written line into a comment. Like the comment block, it is not read, executed, or stored by the program.

```c linenums="1"
//an example for single line comments
```

Single line comments are used to write information about a written command or to explain an operation.

***

## Variables

A variable is a way of naming and storing a numerical value for later use by the program. As their name suggests, variables are numbers that can be continually changed as opposed to constant whose value never changes. A variable needs to be declared and optionally assigned to the value needing to be stored. The following code declares a variable called `inputVariable` and then assigns it the value obtained on analog input pin 2: 

```c linenums="1"
int inputVariable = 0;
inputVariable = analogRead(2);
```

"inputvariable" is the variable itself. The first line declares that it will contain an `int`, short **integer**. The second line sets the variable to the value at analog pin 2. This makes the value of pin 2 accessible elsewhere in the code. 

Once a variable has been assigned, or re-assigned, you can test its value to see if it meets certain conditions, or you can use its value directly. As an example to illustrate three useful operations with variables, the following code tests whether the `inputVariable` is less than 100, if true it assigns the value 100 to `inputVariable`, and then sets a delay based on `inputVariable` which is now a minimum of 100: 

```c linenums="1"
if (inputVariable < 100)
{
    inputVariable = 100;
}
delay(inputVariable);    
```

!!! note
    Variables should be given descriptive names, to make the code more readable. Variable names like tiltSensor or pushButton help the programmer and anyone else reading the code to understand what the variable represents.

### Declaring variables
All variables have to be declared before they can be used. Declaring a variable means defining its value type, as `int`, `float`, `long`, etc., setting a specified name, and optionally assigning an initial value. This only needs to be done once in a program but the value can be changed at any time using arithmetic and various assignments. 

The following example declares that `int` or integer type, and that its initial value equals zero. This is called a simple assignment. 

```c linenums="1"
int inputVariable = 0;
```

A variable can be decared in a number of locations throughout the program and where this definition takes place determines what parts of the program can use the variable. 

### Variable scope
A variable can be declared at the beginning of the program before `setup()`, locally inside of functions, and sometimes within a statement block such as for loops. Where the variabe is declared determines the variable scope, or the ability of certain parts of a program to make use of the variable. 

A global variable is one that can be seen and used by every function and statement in a program. This variable is declared at the beginning of the program, before the `setup()` function. 
 
A local variable is one that is defined inside a function or as part of a for loop. I is only visible and can only be used inside the function in which it was declared. It is therefore possible to have two or more variables of the same name in different parts of the same program that contain different values. Ensuring that only one function has access to its variables simplifies the program and reduces the potential for programming errors. 

The following example shows how to declare a few different types of variables and demonstrates each variable's visibility: 

```c linenums="1"
int value;                //A global variable
void setup()
{
// no setup needed
}

void loop()
{
    for (int localVarForLoop = 0; localVarForLoop<20;) 
    {
        localVarForLoop++;
    }
    float localVarVoidLoop;
}
```

***

## Datatypes

### byte
`byte` stores 8-bit numerical value without decimal points. They have a range of **0** to **255**.

```c linenums="1"
byte someVariable = 180;
```

### int
Integer shortly `int`, is the primary datatype for storage of numbers without decimal points and store a 16-bit value with range of **32,767** to **-32,768**.

```c linenums="1"
int someVariable = 1500;
```

### long
Extended size datatype for long integers, without decimal points, stored in a 32-bit value with range of **2,147,483,647** to **-2,147,483,648**.

```c linenums="1"
long someVariable = 90000; 
```
### float
A datatype for floating-point numbers, or numbers that have a decimal point. Floating-point numbers have greater resolution than integers and are stored as a 32-bit value with a range of  **3.402823E+38** to **-3.4028235E+38**.

```c linenums="1"
float someVariable = 3.14 
```

!!! note
    Floating-point numbers are not exact, and may yield strange results when compared. Floating point math is also much slower than integer math in performing calculations, so should be avoided if possible.

### Arrays
An array is a collection of values that are accessed with an index number. Any value in the array may be called upon by calling the name of the array and the index number of the value. Arrays are zero indexeeed, with the first value in the array beginning at index number 0. An array needs to be declared and optionally assigned values before they can be used. 

```c linenums="1"
int myArray[] = {element0, element1...};
```

Likewise it is possible to declare an array by declaring the array type and size and later assign values to an index position: 

```c linenums="1"
int myArray[5];
myArray[3] = 10; 
```
To retrieve a value from an array, assign a variable to the array and index position: 

```c linenums="1"
x = myArray[3];  //x now equals 10
```
Arrays are often used in `setup()` loops, where the increment counter is also used as the index position for each array value. The following example uses an array to flicker an LED. Using a  `setup()` loop, the counter begins at 0, writes the value contained at index position 0 in the array `flicker[]`, in this case 180, to the PWM pin 10, pauses for 200ms, then moves to the next index position. 

```c linenums="1"
int ledPin = 10;
byte flicker[] = {180, 30, 255, 10, 90, 150, 60};

void setup()
{
    pinMode(ledPin, OUTPUT); 
}

void loop()
{
    for(int i=0; i<7; i++)
    {
        analogWrite(ledPin, flicker[i]);
        delay(200);
    }
}
```
***

## Operators
### Arithmetic
Arithmetic operators include addition, subtraction, multiplication, and division. They return the sum, difference, product, or quotient (respectively) of two operands. 

- `+` Addition
- `-` Subtraction
- `*` Multiplication
- `/` Division
- `%` Modulo

```c linenums="1"
y = y + 3;
x = x - 7;
i = j * 6;
r = r / 5;
```

The operation is conducted using the data type of the operands, so, for example, 7/2 results in 3 instead of 3.5 since 7 and 2 are ints and are incapable of using decimal points. This also means that the operation can overflow if the result is larger than what can be stored in the data type.

If the operands are of different types, the larger type is used for the calculation. For example, if one of the numbers (operands) are of the type <code class="one-line">float</code> and the other of type <code class="one-line">integer</code>, floating point math will be used for the calculation.

!!! note
    Use the cast operator to convert one variable type to another on the fly. For example, <code class="one-line">a = (int)3.14</code> will set a equal to 3.

### Compound assignments
Compound assignments combine an arithmetic operation with a variable assignment. These are commonly found in for loops as described later. The most common compound assignments include: 

```c linenums="1"
x++     //x = x + 1
x--     //x = x - 1
x += y  //x = x + y
x -= y  //x = x - y
x *= y  //x = x * y
x /= y  //x = x / y
```
### Comparison operators
Comparisons of one variable or constant against another are often used in if statements to test if a specified condition is true. In the example found on the following pages, ?? is used to indicate any of the following conditions: 

- `==` Equal to
- `!=` Not equal to
- `<` Less than
- `>` Greater than
- `<=` Less than or equal to
- `>=` Greater than or equal to

```c linenums="1"
x == y  //x is equal to y
x != y  //x is not equal to y
x <  y  //x is less than y
x >  y  //x is greater than y
x <= y  //x is less than or equal to y
x >= y  //x is greater than or equal to y
```

### Logical operators
Logical operators are usually a way to compare two expressions and return a <code class="one-line">TRUE</code> or <code class="one-line">FALSE</code> depending on the operator. There are three logical operators, <strong>AND</strong>, <strong>OR</strong> and <strong>NOT</strong>, that are often used in if statements: 

- `&&` Logical AND
- `||` Logical OR
- `!` Logical NOT

Logical <strong>AND</strong>: 

```c linenums="1"
if (x > 0 && x < 5)     //true only if both
                        //expressions are true
```
Logical <strong>OR</strong>:

```c linenums="1"
if (x > 0 || x < 5)     //true if either
                        //expression is true
```

Logical <strong>NOT</strong>:

```c linenums="1"
if (!x > 0)             //true only if
                        //expression is false
```

There is a logical truth table listed below, which can be used later: 


|   A   |   B   | A(AND)B | A(OR)B | NOT A | NOT B |
|:-----:|:-----:|:-------:|:------:|:-----:|:-----:|
|  TRUE |  TRUE |   TRUE  |  TRUE  | FALSE | FALSE |
|  TRUE | FALSE |  FALSE  |  TRUE  | FALSE |  TRUE |
| FALSE |  TRUE |  FALSE  |  TRUE  |  TRUE | FALSE |
| FALSE | FALSE |  FALSE  |  FALSE |  TRUE |  TRUE |

!!! note
    Use parentheses to group expressions and clarify order of operations.

***

## Constants

Constants are fixed values that do not change during program execution.

### Defining Constants

Use the `const` keyword to define a constant:

```c linenums="1"
const int ledPin = 13;
```

!!! note
    Constants help make your code more readable and prevent accidental changes.

### Predefined Constants

Arduino provides some predefined constants, such as `HIGH`, `LOW`, `INPUT`, and `OUTPUT`.

***

## Control flow
### if
if statements test whether a certain condition has been reached, such as an analog value being above a certain number, and executes any statements inside the brackets if the statement is true. If false the program skips over the statement. The format for an `if` test is: 

```c linenums="1"
if (someVariable ?? value) // ?? can be one of: <, >, <=, >=, ==
{
    doSomething; 
}
```

The above example compares `someVariable` to another value, which can be either a variable or constant. If the comparison, or condition in parantheses is true, the statements inside the brackets are run. If not, the program skips over them and continues on after the brackets. 

!!! note
    The `??` symbol in this example used instead of Operators (Look at Operators section). Beware of accidentally using "=" instead of  "==" when comparing!

### if... else
`if... else` allows for 'either-or' decisions to be made. For example, if you wanted to test a digital input, and do one thing if the input went `HIGH` or instead do another thing if the input was `LOW`, you would write that this way: 

```c linenums="1"
if (inputPin == HIGH)
{
    doThingA;
}
else
{
    doThingB;
}
```

`else` can also precede another if test, so that multiple, mutually exclusive tests can be run at the same time. It is even possible to have an unlimited number of these else branches. Remember though, only one set of statements will be run depending on the condition tests: 

```c linenums="1"
if (inputPin < 500)
{
    doThingA;
}
else if (inputPin >= 1000)
{
    doThingB;
}
else
{
    doThingC;
}
```


### for
The for statement is used to repeat a block of statements enclosed in curly braces a specified number of times. An increment counter is often used to increment and terminate the loop. There are three parts, seperated by semicolons (;) to the for loop header: 

```c linenums="1"
for (initialization; condition; expression)
{
    doSomething;
}
```

The initialization of a local variable, or increment counter, happens first and only once. Each time through the loop, the following condition is tested. If the condition remains true, the following statements and expression are executed and the condition is tested again. When the condition becomes false, the loop ends. 

The following example starts the integer `i` at 0, tests to see if i is still less than 20 and if true, increments i by 1 and executes the enclosed statements: 

```c linenums="1"
for (int i=0; i<20; i++) 
{                          
    digitalWrite(13, HIGH);
    delay(250);            
    digitalWrite(13, LOW); 
    delay(250);         
}
```

### while
`while` loops will loop continously, and infinitely, until the expression inside the paranthesis becomes false. Something must change the tested variable, or the while loop will never exit. This could be in your code, such as an incremented variable, or an external condition, such as testing a sensor. 

```c linenums="1"
while (someVariable ?? value)
{
    doSomething;
}
```

The following example tests whether `someVariable` is less than 200 and if true executes the statements inside the brackets and will continue looping until 'someVariable' is no longer less than 200. 

```c linenums="1"
while (someVariable < 200) 
{
    doSomething;          
    someVariable++;
}
```

### do... while
The `do... while` loop works in the same manner as the while loop, with exception that the condition is tested at the end of the loop, so the do loop will always run at least once. 

```c linenums="1"
do 
{
    doSomething;
} while (someVariable ?? value);
```

The following example assigns `readSensors();` to the variable `x`, pauses for 50 milliseconds, then loops indefinitely until 'x' is no longer less than 100: 

```c linenums="1"
do
{
    x = readSensors();
    delay(50);         
} while (x < 100);  
```

***