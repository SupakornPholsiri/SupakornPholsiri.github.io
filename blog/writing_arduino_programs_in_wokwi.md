---
layout: default
title: Writing Arduino programs in Wokwi
description: Writing basic Arduino C/C++ Programs in Wokwi Web-based Smmimulator.
---

[<< Main Page](https://supakornpholsiri.github.io/)

# Writing Arduino programs in Wokwi
In this blog, I will write about writing basic Arduino programs in Wokwi Web-based Simulator.

## Program #1
LED changing pattern: A \
Step 1. Initially, only one LED (at index=0) is ON, and the rest of the LEDs are OFF. \
Step 2. The position of the ON LED should be moved to the next in a circular manner in a fixed time interval and then repeat Step 2.

Let's start by defining the pin numbers that we are going to use.
```C
#if defined(ESP32)
const int LED_PINS[] = {23,22,32,33,25,26,27,14,12,13};
#else
const int LED_PINS[] = {2,3,4,5,6,7,8,9,10,11};
#endif
```
This piece of code defines pin numbers according to whether you are using ESP32 board or not. If you're using ESP32 board then the first list will be used. otherwise the second list will be used.

```C
const int NUM_LEDS = sizeof(LED_PINS)/sizeof(int);
```
This piece of code calculates the amount of pins we are going to use by dividing the size of pin numbers list in bytes by the size of an integer in bytes.

```C
void setup() {
  for ( int i=0; i < NUM_LEDS; i++ ) {
    // set the direction of the i-th LED pin
    pinMode( LED_PINS[i], OUTPUT ); 
    // turn on the first LED (i=0) and the rest off. 
    digitalWrite( LED_PINS[i], (i==0) ? HIGH : LOW );
  }
}
```

```C
void loop() {
  // set a static value to keep track of which LED to turn on
  static uint16_t value=0;
  // reset the static value after it reaches 10
  if (value == 10) {value = 0;}
  for ( int i=0; i < NUM_LEDS; i++ ) {
    if (i == value) {digitalWrite(LED_PINS[i], HIGH);}
    else {digitalWrite(LED_PINS[i], LOW);}
  }
  value++;
  delay(500); 
}
```

## Program #2
LED changing pattern: B \
Step 1. Initially, all LEDs are OFF. \
Step 2. Turn on the LEDs one by one with a time delay, starting at index=0 until all LEDs are ON. \
Step 3. If all LEDs are ON, turn off LEDs one by one starting at index=n-1,  where n is the total number of LEDs, until all LEDs are OFF, and repeat Steps 2-3.

## Program #3
LED changing pattern: C \
Step 1. Initially, all LEDs are OFF. \
Step 2. Turn on the first LED by increasing the duty cycle of the PWM signal driving the LED, until the LED is fully ON. \
Step 3. Repeat Step 2 with the next LED until all LEDs are fully ON. \
Step 4. If all LEDs are ON, turn off LEDs one-by-one by decreasing the duty cycles of the PWM signals until all LEDs are OFF and repeat Steps 2-4.

## Program #4
LED changing pattern: D \
Step 1. Initially, all LEDs are OFF. \
Step 2. Turn on the first 4 LEDs using PWM signals, each with different duty cycles (e.g. 100%, 50%, 25%, 10%), and the rest of the LEDs are OFF. \
Step 3. Move the positions of ON LEDs to the left by one position in a circular manner and repeat Step 3.

## Program #5

## Program #6
