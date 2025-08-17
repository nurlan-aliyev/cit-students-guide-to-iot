# Input/Output Operation
## Digital I/O
### pinMode(pin,  mode), 
Used in `void setup()` to configure a specified pin to behave either as an INPUT or an OUTPUT.

```c linenums="1"
pinMode(pin, OUTPUT);  //sets pin as OUTPUT
```

Arduino digital pins default to inputs, so they don't need to be explicitly declared as inputs with `pinMode()`. Pins configured as `INPUT` are said to be in high-impedance state.  

There are also convenient 20k pullup resistors built into the Atmega chip can be accessed from software. These built-in pullup resistors are accesed in the following manner: 

```c linenums="1"
pinMode(pin, INPUT);  
digitalWrite(pin, HIGH); 
```

Pins configured as `OUTPUT` are said to be in a low-impedance state and can provide 40mA (milliamps) of current to other devices. This is enough current to brightly light up an LED, but not enough current to run most relays, solenids, or motors. 

Short circuits on Arduino pins and excessive current can damage or destroy the output pin, or damage the entire Atmega chip. It is often a good idea to connect an `OUTPUT` pin to an external device in series with a 470 or 1k ohms resistors.

### digitalRead(pin)  
Reads the value from a specified digital pin with the result either `HIGH` or `LOW`. The pin can be specified as either a variable or constant (0-13). 

```c linenums="1"
    value = digitalRead(pin); 
```

### digitalWrite(pin, value)
Outputs either logic level `HIGH` or `LOW` at a specified digital pin. The pin can be specified as either a variable or constant (0-13). 

```c linenums="1"
digitalWrite(pin, HIGH); 
```
The following example reads a pushbutton connected to a digitak input and turns on a LED connected to a digital output when the button has been pressed: 

```c linenums="1"
int led = 13;     //LED on pin 13
int pushButton  = 7;  //pushbutton on pin 7
int value = 0;    //variablle to read value

void setup()
{
    pinMode(led, OUTPUT); 
    pinMode(pushButton, INPUT);   
}

void loop()
{
    value = digitalRead(pushButton);  
    digitalWrite(led, value);         
}
```
***

## Analog I/O

### analogRead(pin)
Reads the value from a specified analog pin with a 10-bit resolution. This pin only works on analog in pins (0-5). The result varies from 0 to 1023. 

```c linenums="1"
value = analogRead(pin); 
```
!!! note
    Analog pins do not require to be first declared as `INPUT` nor `OUTPUT`.

### analogWrite(pin, value)
Writes a pseudo-analog value using hardware enabled pulse width modulation (PWM) to an output pin marked PWM. On newer Arduinos with the ATmega168 chip, this function works on pins 3, 5, 6, 9, 10 and 11. Older Arduinos only supports 9, 10 and 11. The value can be specified as a variable or constant with a value from 0-255. 

```c linenums="1"
analogWrite(pin, value);  
```

A value of 0 generates a steady 0 volts output at the specified pin. A value of 255 generates a steady 5 volts output at the specified pin. For values in between 0-255, the pin rapidly alternates between 0 and 5 volts. 

Because this is a hardware function, the pin will generate a steady wave after a call to analogWrite in the background until the next call to analogWrite (or a call to digitalRead or digitalWrite on the same pin).

```c linenums="1"
int led = 10; //LED with 220 resist. on pin 10
int pin = 0;  //potentiometer on analog pin 0
int value;    //value for reading

void setup(){} 

void loop()
{
    value = analogRead(pin); 
    value /= 4;   //converts 0-1023 to 0-255
    analogWrite(led, value); 
}
```

***