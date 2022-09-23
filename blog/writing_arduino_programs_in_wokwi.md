---
layout: default
title: Writing Arduino programs in Wokwi
description: Writing basic Arduino C/C++ Programs in Wokwi Web-based Smmimulator.
---

[<< Main Page](https://supakornpholsiri.github.io/)

# Writing Arduino programs in Wokwi
In this blog, I will write about writing basic Arduino programs in Wokwi Web-based Simulator.

## Program #1
![Circuit for program 1](/assets/images/PatternA.png)

LED changing pattern: A \
Step 1. Initially, only one LED (at index=0) is ON, and the rest of the LEDs are OFF. \
Step 2. The position of the ON LED should be moved to the next in a circular manner in a fixed time interval and then repeat Step 2.

```C
#if defined(ESP32)
const int LED_PINS[] = {23,22,32,33,25,26,27,14,12,13};
#else
const int LED_PINS[] = {2,3,4,5,6,7,8,9,10,11};
#endif
```
Define pin numbers according to whether you are using ESP32 board or not. If you're using ESP32 board then the first list will be used. otherwise the second list will be used.

```C
const int NUM_LEDS = sizeof(LED_PINS)/sizeof(int);
```
Calculate the amount of pins we are going to use by dividing the size of pin numbers list in bytes by the size of an integer in bytes.

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
Set direction of LED pins according to the initial conditions.

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
Turn the next LED on and turn all other LED off. Wait 500 ms. Then repeat.


## Program #2
LED changing pattern: B \
Step 1. Initially, all LEDs are OFF. \
Step 2. Turn on the LEDs one by one with a time delay, starting at index=0 until all LEDs are ON. \
Step 3. If all LEDs are ON, turn off LEDs one by one starting at index=n-1,  where n is the total number of LEDs, until all LEDs are OFF, and repeat Steps 2-3.

```C
#if defined(ESP32)
const int LED_PINS[] = {23,22,32,33,25,26,27,14,12,13};
#else
const int LED_PINS[] = {2,3,4,5,6,7,8,9,10,11};
#endif
```
Define pin numbers according to whether you are using ESP32 board or not. If you're using ESP32 board then the first list will be used. otherwise the second list will be used.

```C
const int NUM_LEDS = sizeof(LED_PINS)/sizeof(int);
```
Calculate the amount of pins we are going to use by dividing the size of pin numbers list in bytes by the size of an integer in bytes.

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
Set direction of LED pins according to the initial conditions.

```C
void loop() {
  // Turn on the LEDs one by one with a time delay, starting from index 0.
  for ( int i=0; i < NUM_LEDS; i++ ) {
    digitalWrite(LED_PINS[i], HIGH);
    delay(500);
  }
  // Turn off the LEDs one by one with a time delay, starting from the last index.
  for ( int i=NUM_LEDS-1; i >= 0; i-- ) {
    digitalWrite(LED_PINS[i], LOW);
    delay(500);
  }
}
```
Turn on the LEDs one by one with a time delay, starting from index 0. After all the LEDs are on, Turn off the LEDs ono by one with a time delay, starting form the last index. Then repeat the process.

## Program #3
LED changing pattern: C \
Step 1. Initially, all LEDs are OFF. \
Step 2. Turn on the first LED by increasing the duty cycle of the PWM signal driving the LED, until the LED is fully ON. \
Step 3. Repeat Step 2 with the next LED until all LEDs are fully ON. \
Step 4. If all LEDs are ON, turn off LEDs one-by-one by decreasing the duty cycles of the PWM signals until all LEDs are OFF and repeat Steps 2-4.

```C
const int LED_PINS[] = {5,18,19,21};
const int NUM_LEDS   = sizeof(LED_PINS)/sizeof(int);
```
Define pin numbers that we are going to use and calculate the amount of pins that we are going to use.

```C
#define OFF (LOW)
#define ON (HIGH)
```
Since we are using active HIGH LEDs. We define HIGH as ON and define LOW as OFF.

```C
void setup() {
  
}
```
Since we are not setting anything up before the main code, we are going to leave the void setup() blank.

```C
const int PWM_RESOLUTION = 8;
const int PWM_FREQ = 1000;
const int DUTY_MAX = (1 << PWM_RESOLUTION);
```
Placeholder text

```C
void turn_on() {
  for ( int i=0; i < NUM_LEDS; i++ ) {
      ledcSetup( i /*channel*/, PWM_FREQ, PWM_RESOLUTION );
      ledcAttachPin( LED_PINS[i] /*pin*/, i /*channel*/ );
      for ( int x=0; x < DUTY_MAX; x++ ) { 
         ledcWrite( i, x );
         delay(5);
      }
      ledcDetachPin( LED_PINS[i] ); 
      digitalWrite( LED_PINS[i], ON );
      delay(200);
  }
}
```
Placeholder text

```C
void turn_off() {
  for ( int i=0; i < NUM_LEDS; i++ ) {
      ledcSetup( i /*channel*/, PWM_FREQ, PWM_RESOLUTION );
      ledcAttachPin( LED_PINS[i] /*pin*/, i /*channel*/ );
      for ( int x=0; x < DUTY_MAX; x++ ) { 
         ledcWrite( i, DUTY_MAX-1-x );
         delay(5);
      }
      ledcDetachPin( LED_PINS[i] ); 
      digitalWrite( LED_PINS[i], OFF );
      delay(200);
  }
}
```
Placeholder text

```C
void loop() {
  turn_on();
  turn_off();
}
```
Run the turn_on function and the turn_off function. Then repeat.

## Program #4
LED changing pattern: D \
Step 1. Initially, all LEDs are OFF. \
Step 2. Turn on the first 4 LEDs using PWM signals, each with different duty cycles (e.g. 100%, 50%, 25%, 10%), and the rest of the LEDs are OFF. \
Step 3. Move the positions of ON LEDs to the left by one position in a circular manner and repeat Step 3.

```C
const int LED_PINS[] = {32,33,25,26,27,14,12,13};
const int NUM_LEDS   = sizeof(LED_PINS)/sizeof(int);
```
Define pin numbers that we are going to use and calculate the amount of pins that we are going to use.

```C
#define OFF (LOW)
#define ON (HIGH)
```
Since we are using active HIGH LEDs. We define HIGH as ON and define LOW as OFF.

```C
const int PWM_RESOLUTION = 8;
const int PWM_FREQ = 1000;
const int DUTY_MAX = (1 << PWM_RESOLUTION);
```
Placeholder text.

```C
void setup() {
  for (int i=0; i < NUM_LEDS; i++) {
    ledcSetup( i /*channel*/, PWM_FREQ, PWM_RESOLUTION );
    ledcAttachPin( LED_PINS[i] /*pin*/, i /*channel*/ );
  }
}
```
Placeholder text

```C
void loop() {
  static uint16_t value_1=0;
  static uint16_t value_2=1;
  static uint16_t value_3=2;
  static uint16_t value_4=3;
  // put your main code here, to run repeatedly:
  for ( int i=0; i < NUM_LEDS; i++ ) {
    if (i == value_1){
      ledcWrite(i, (DUTY_MAX-1)*10/100);
    }else if (i == value_2) {
      ledcWrite(i, (DUTY_MAX-1)*25/100);
    }else if (i == value_3) {
      ledcWrite(i, (DUTY_MAX-1)*50/100);
    }else if (i == value_4) {
      ledcWrite(i, DUTY_MAX-1);
    }else {ledcWrite(i, 0);}
  }
  value_1 = (value_1+1) % NUM_LEDS;
  value_2 = (value_2+1) % NUM_LEDS;
  value_3 = (value_3+1) % NUM_LEDS;
  value_4 = (value_4+1) % NUM_LEDS;
  delay(500);
}
```
Placeholder text

## Program #5

```C
#include "Pin.h"
```
Include the Pin.h Header file.

```C
const int LED_PINS[] = {23,22,32,33,25,26,27,14,12,13};
const int NUM_LEDS = sizeof(LED_PINS) / sizeof(int);
```
Define pin numbers that we are going to use and calculate the amount of pins that we are going to use.

```C
void setup(){
   
}
```
Since we are not setting anything up before the main function, we can leave the setup() blank.

```C
void loop(){
   // set a static value to keep track of which LED to turn on
   static int value=0;
   // reset the value after it reaches 10.
   if (value == 10) {value = 0;}
   // turn the LED corresponding to the static value on. Turn all other LEDs off.
   for (int i = 0; i < NUM_LEDS; i++){
      // create a PIN class object with OUT direction and set its value according to which LEDs should be turned on.
      Pin pin(LED_PINS[i], Pin::Direction::OUT, (i == value) ? HIGH : LOW);
   }
   value++;
   delay(500);
}
```
Turn the first LED on and turn all other LED off. Wait 500 ms. Then turn the next LED on and turn all other LEDs off. Repeat this step for all LED. Once the last LED has been turned on, Do the entire main function again starting form the first LED.

[See the full code in action here](https://wokwi.com/projects/343504328318779988)

## Program #6

```C
#include "Pin.h"
```
Include the Pin.h Header file.

```C
const int LED_PINS[] = {23,22,32,33,25,26,27,14,12,13};
const int NUM_LEDS = sizeof(LED_PINS) / sizeof(int);
```
Define pin numbers that we are going to use and calculate the amount of pins that we are going to use.

```C
void setup(){
   
}
```
Since we are not setting anythin up before the main function, we can leave setup blank.

```C
void loop(){
   // 
   for (int i = 0; i < NUM_LEDS; i++){
      Pin pin(LED_PINS[i], Pin::Direction::OUT, HIGH);
      delay(500);
   }
   for (int i = NUM_LEDS-1; i >= 0; i--){
      Pin pin(LED_PINS[i], Pin::Direction::OUT, LOW);
      delay(500);
   }
}
```
