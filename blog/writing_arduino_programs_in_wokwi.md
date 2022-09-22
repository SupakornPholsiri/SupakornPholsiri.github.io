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
