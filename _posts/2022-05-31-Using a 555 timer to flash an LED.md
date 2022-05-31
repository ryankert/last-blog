---
layout: article
title: Using a 555 timer to flash an LED
tags: Electronic Circuit
key: 2022-05-31-Using a 555 timer to flash an LED
---

## What is a 555 timer?
- Pin 1. – Ground, The ground pin connects the 555 timer to the negative (0v) supply rail.
- Pin 2. – Trigger, The negative input to comparator No 1. A negative pulse on this pin “sets” the internal Flip-flop when the voltage drops below 1/3Vcc causing the output to switch from a “LOW” to a “HIGH” state.
- Pin 3. – Output, The output pin can drive any TTL circuit and is capable of sourcing or sinking up to 200mA of current at an output voltage equal to approximately Vcc – 1.5V so small speakers, LEDs or motors can be connected directly to the output.
- Pin 4. – Reset, This pin is used to “reset” the internal Flip-flop controlling the state of the output, pin 3. This is an active-low input and is generally connected to a logic “1” level when not used to prevent any unwanted resetting of the output.
- Pin 5. – Control Voltage, This pin controls the timing of the 555 by overriding the 2/3Vcc level of the voltage divider network. By applying a voltage to this pin the width of the output signal can be varied independently of the RC timing network. When not used it is connected to ground via a 10nF capacitor to eliminate any noise.
- Pin 6. – Threshold, The positive input to comparator No 2. This pin is used to reset the Flip-flop when the voltage applied to it exceeds 2/3Vcc causing the output to switch from “HIGH” to “LOW” state. This pin connects directly to the RC timing circuit.
- Pin 7. – Discharge, The discharge pin is connected directly to the Collector of an internal NPN transistor which is used to “discharge” the timing capacitor to ground when the output at pin 3 switches “LOW”.
- Pin 8. – Supply +Vcc, This is the power supply pin and for general purpose TTL 555 timers is between 4.5V and 15V.

The 555 Timers name comes from the fact that there are three 5kΩ resistors connected together internally producing a voltage divider network between the supply voltage at pin 8 and ground at pin 1. The voltage across this series resistive network holds the negative inverting input of comparator two at 2/3Vcc and the positive non-inverting input to comparator one at 1/3Vcc.

The two comparators produce an output voltage dependent upon the voltage difference at their inputs which is determined by the charging and discharging action of the externally connected RC network. The outputs from both comparators are connected to the two inputs of the flip-flop which in turn produces either a “HIGH” or “LOW” level output at Q based on the states of its inputs. The output from the flip-flop is used to control a high current output switching stage to drive the connected load producing either a “HIGH” or “LOW” voltage level at the output pin.

![](https://i.imgur.com/wRWSJt4.gif)

> **Usage**
> The most common use of the 555 timer oscillator is as a simple astable oscillator by connecting two resistors and a capacitor across its terminals to generate a fixed pulse train with a time period determined by the time constant of the RC network. But the 555 timer oscillator chip can also be connected in a variety of different ways to produce Monostable or Bistable multivibrators as well as the more common Astable Multivibrator.

## Circuits

- Resistors * 3
- 9V battery
- NE555 Timer
- Capacitor

![](https://i.imgur.com/3RKgRDD.png)

## How?

- Capacitor (c1): control how much time it delays
