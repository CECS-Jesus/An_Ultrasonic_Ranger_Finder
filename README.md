# An Ultra Sonic Ranger Finder

## Introduction
This project involves creating an embedded system that utilizes a Phase Locked Loop (PLL) to produce a 40MHz clock. The system features a Systick timer to generate an accurate 5Hz square wave, an Ultrasonic Sensor, and LEDs whose brightness is controlled via software-based timer PWM. The system is capable of detecting the distance of an object from the sensor and adjusting the LED brightness and color accordingly.

## Theory

### Phase Locked Loop (PLL)
PLL is used to generate a stable high-frequency output from a low-frequency input. For this project, a 40 MHz frequency is generated by dividing the 400 MHz bus frequency by SYSDIV2+1. Setting the value of SYSDIV2 to 9 results in a 40 MHz frequency \[ 400Mhz/(9+1) = 40Mhz \].

### General Purpose Timer
The General Purpose Timer 1, a 32-bit countdown timer, is used to generate precise trigger pulses for measuring the ultrasonic sensor's echo high period. Rising and falling edge interrupts are utilized to detect the edges of the interrupts for the echo pin.

### Distance Calculation
The distance of an object in front of the sensor is calculated using a mathematical equation within the code.
The duration is determined within the TIMER1 module.

### Pulse Width Modulation (PWM)
PWM is employed to control the LED brightness. The closer an object is to 10 cm from the sensor, the brighter the LED gets. If the object is farther than 70 cm, the LED turns off.

#### LED Behavior
- **Less than 10cm**: Red LED blinks at 2Hz.
- **Between 10cm and 70cm**: White LED brightness varies.
- **Greater than 70cm**: LED turns off.

## Demo Video
A demonstration of the system in action can be found in this video
https://youtu.be/2qrtmd1UbZQ

---

