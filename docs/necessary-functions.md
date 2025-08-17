# Some necessary functions

## delay(milliseconds)
Pauses your program for the amount of time as specified in milliseconds, where 1000 equals 1 second. 

```c linenums="1"
delay(1000);      //waits for one second
```

## millis()
Returns the number of milliseconds since the Arduino board began running the current program as an unsigned long value. 

```c linenums="1"
value = millis(); //sets value equal to millis() 
```

!!! note
    This number will overflow (reset back to zero), after approximately 9 hours.

## min(x, y)
Calculates the minimum of two numbers of any data type and returns the smaller number. 
```c linenums="1"
value = min(value, 100);
```         

## max(x, y) 
Calculates the maximum of two numbers of any data type and returns the larger number. 

```c linenums="1"
value = max(value, 100);
```

## randomSeed(seed) 
Sets a value, or seed, as the starting point for the `random()` function.

```c linenums="1"
randomSeed(value);
```
Because the Arduino is unable to create a truly random number, randomSeeed allows you to place a variable, constant, or other function into the random function, which helps to generate more random **"random"** numbers. There are a variety of different seeds, or functions, that can be used in this function includong millis() or even `analogRead()` to read electrical noise through an analog pin. 

## random(max) or random(min, max) 
The random function allows you to return pseudo-random numbers within a range specified by min and max values. 

```c linenums="1"
value = random(100, 200);
```                               
!!! note
    Use this after using the `randomSeed()` function.

The following example creates a random value between 0-255 and outputs a PWM signal on a PWM pin equal to random value: 

```c linenums="1"
int ranNumber;  //variable to store the random value
int led = 10;   //LED with 220 resistor on pin 10

void setup() {}   //no setup needed

void loop()
{
    randomSeed(millis());  //sets millis() as the seed
    randNumber = random(255);  //random number from 0-255
    analogWrite(led, randNumber); //outputs PWM signal
    delay(500);                   //pauses for half a second
}
```

## Serial.begin(rate)
Opens serial port and sets the baud rate for serial data transmission. The typical baud rate for comminucating with the computer is 9600 although other speeds are supported. 

```c linenums="1"
void setup()
{
    Serial.begin(9600); //opens serial port sets data rate to 9600
}
```
!!! note
    When using serial communication, digital pins 0 (RX) and 1 (TX) cannot be used at the same time.

## Serial.println(data) 
Prints data to the serial port, followed by an automatic carriage return and line feed. This command takes the same form as `Serial.print()`, but is easier for reading data on the Serial Monitor. 

```c linenums="1"
Serial.println(analogValue); //prints the value of analogValue
```

!!! note
    For more information on the various permutations of the Serial.println() and Serial.print() functions please refer to the Arduino website.

The following simple example takes a reading from analog pin 0 and sends this data to the computer every 1 second. 

```c linenums="1"
void setup()
{
    Serial.begin(9600);
}

void loop()
{
    Serial.println(analogRead(0)); 
    delay(1000);                   
}
```
***