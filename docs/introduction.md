# Introduction to IoT and Arduino
## What is "Arduino"?
Arduino is an open-source electronics platform designed for ease of use, combining simple hardware and software. Arduino boards can receive inputs, such as signals from sensors, button presses, or online messages, and respond by controlling outputs like motors, LEDs, or publishing data online. You program the board by sending instructions to its microcontroller using the Arduino programming language (derived from [Wiring](https://en.wikipedia.org/wiki/Wiring_(software))) and the Arduino Software (IDE), which is built on top of [Processing](https://en.wikipedia.org/wiki/Processing).

Arduino has powered countless projects, ranging from everyday gadgets to advanced scientific tools. Its global community includes students, hobbyists, artists, programmers, and professionals, all contributing to a vast pool of shared knowledge that benefits both beginners and experts.

Originally developed at the [Ivrea Interaction Design Institute](https://en.wikipedia.org/wiki/Interaction_Design_Institute_Ivrea), Arduino was intended as a quick prototyping tool for students without technical backgrounds. As its popularity grew, the platform evolved to meet new demands, expanding from basic boards to products for IoT, wearables, 3D printing, and embedded systems.

??? note "More on the history of Arduino"

    In 2001, *Casey Reas* and *Benjamin Fry* launched a project called **_Processing_**.
    The aim of this project was to encourage non-programmers to write programs quickly and easily.
    The project allows the user to test their ideas and experiment on digital sketchbooks.  This project gave rise to new ideas for conducting experiments in the physical world.
    In 2003, *Hernando Barragán* began working on a microcontroller called **_Wiring_**, which has the same principle of operation as Processing.
    This board played a major role in the creation of the Arduino.

    In partnership with the Processing project, the Wiring project also aimed to attract artists, designers and other creative people.
    However, unlike the Processing project, Wiring involved more electronics than programming.
    Although the wiring board was cheaper than some other microcontrollers (PIC, etc.), it was a high-cost investment for students.

    In 2005, the **_Arduino_** project was launched as a more affordable and easy-to-use device for students at the institute.
    The creators are said to have named the project in honor of King Arduin of Italy.
    According to some, this name is associated with the name of the brewery near the institute.


    The Arduino project uses a lot of experience from both Wiring and Processing projects.
    For example, a graphical user interface (**GUI**) similar to that in the Processing project is used in Arduino.
    Although the interface is from the Processing project, it has been customized for the Arduino.

    Arduino also uses the Processing project's approach when naming coded projects, calling them *sketch*es. In this program you will be informed about many sketches and you will be able to check them.

    The Arduino board was more 'compassionate' and powerful than the Wiring and previous microcontrollers.
    Students and even professionals could easily damage Wiring and other microcontrollers due to incorrect wiring.
    This problem was not only financial, but also caused delays in projects.

    It is also possible to replace the microcontroller chip on the Arduino board, so that if it becomes unusable, you can simply replace the chip instead of the full board.
    Another important difference is that Arduino boards are cheaper and more profitable than others, and in 2006 the **_Basic Stamp_** board was sold twice as expensive as the Arduino board.

## Why Choose Arduino?
Arduino’s straightforward and accessible design has made it popular for a wide range of projects. The software is beginner-friendly but also offers flexibility for advanced users, and it works on Mac, Windows, and Linux. Educators and students use Arduino for affordable scientific instruments, demonstrations of scientific principles, and learning programming and robotics. Designers, architects, musicians, and artists use it for interactive prototypes and creative installations. Makers use Arduino for projects showcased at events like Maker Faire. Arduino is a valuable tool for learning and experimentation, with resources and community support available for everyone.

## About Microcontrollers 

At the heart of the Arduino lies a microcontroller that has the ability to perform logical operations at speeds and accuracy that humans cannot.

You can even create systems that are in close contact with the real world. For example, it is possible to create smart home, greenhouse and even garden systems, which can minimize human labor and impact and perform almost all the work in a timely and accurate manner.

Microcontrollers are small and do not take up much space and do not require much power for operation.
Well, how small? Physically, the microcontrollers that come with the Arduino are in captured form.

The microcontroller is rectangular in shape, mounted on a blue PCB. However, this does not mean that all microcontrollers are of this size, they can be in small-microscopic forms, ranging in size and function.

In addition to the main processor core, which you specify, there is RAM (Random Access Memory) on the chip to store commands during program execution. It also has input and output devices that can communicate with the environment or other computers.

Microcontrollers were invented in the early 1970s to perform a variety of automation tasks in the industry.
The current Arduino board includes an ATmega328 microprocessor from Atmel, a family of AVR chips. These microprocessors were first created in the early 1990s.

One of the advantages of microcontrollers is that they are cheaper than microprocessors for phones, computers and other devices. This is because of their limited abilities.

Because they are designed to either control something or react to signals received from sensors.

Because they are cheap, you can use them in all kinds of small computational tasks, e.g. garage door, etc. you can automate devices with code.

The microcontroller placed on the Arduino board is very cheap, and the reason why the board is more valuable is the other important devices placed on it, which help you to facilitate your work.