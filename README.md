https://github.com/user-attachments/assets/b181001b-00b4-43b8-9d5b-1cbc16d668c2


**Project Website:** https://andrewcongdon14.wixsite.com/andrew-congdon

# Star Tours: The Adventures Continue - Model Ride Vehicle

This repository contains the Arduino code for a fully functional Star Tours model ride vehicle, created as a final project for the *Introduction to Droid Building* course at the University of Notre Dame in Fall 2024.

Inspired by the Disney Parks attraction *Star Tours – The Adventures Continue*, this scaled model ride vehicle showcases synchronized lighting, motion, sound, and visual effects to simulate three immersive ride sequences, all within a compact 5x5 ft performance space.

---

## Project Overview

The Star Tours ride vehicle is equipped with:
- **Precision motor control** for smooth manual and automated movement
- **Color sensor navigation** for autonomous travel along colored paths
- **Three 90-second ride sequences**, each representing a narrative arc from the attraction:
  - **Routine 1** – Takeoff, Rebel Spy Reveal, and Hyperjump Escape
  - **Routine 2** – Tatooine Podrace and Yoda Transmission
  - **Routine 3** – Boba Fett Ambush, Death Star Bomb, and Landing
- **Programmable lighting effects** via NeoPixels and PWM LEDs
- **Interactive PS3 controller integration** for manual override and mode switching
- **Onboard MP3 audio** synchronized with movements and visuals
- **TFT display animations** showcasing themed Star Wars images

---

## Control Modes

### Manual Mode
- Controlled via PS3 controller
- Real-time motion using joystick input
- Ambient lighting and audio loops active during idle

### Auto Mode
- Activated by pressing the triangle button
- Follows a colored track:
  - **Blue** → Go Forward
  - **Red** → Turn Right
  - **Green** → Turn Left

### Routine Mode
- Three pre-scripted ride sequences triggered with the D-pad:
  - `LEFT` – Routine 1: Darth Vader & Hyperjump
  - `UP` – Routine 2: Podracing & Yoda
  - `RIGHT` – Routine 3: Boba Fett, Sonic Bomb, and Death Star Escape

---

## Features

- **Smooth speed ramping** for realistic movement transitions
- **Custom ambient audio engine** with over a dozen randomized sounds
- **Modular lighting functions**: thruster flicker, fire effects, rainbow cycle, hyperspace jump, and more
- **R2-D2-inspired servo animation** tied to key sound/visual moments
- **TFT screen image library** displaying 18 different Star Wars-themed scenes
- **Scene and movement arrays** for precise synchronization of lights, sound, and motion

---

## Hardware Components

- Arduino Mega 2560
- SABER 2X12 Motor Controller
- Robertsonics MP3 Trigger + microSD
- Adafruit ST7735 TFT Display
- Adafruit 24-Channel PWM Driver
- TCS3200 Color Sensor
- MG90S Servo (for top animation)
- 2x NeoPixel LED strips (interior lighting)
- 10+ additional PWM LEDs for headlights, thrusters, and ambient FX
- Precision planetary gear motors + omni wheel (drive system)
- PS3 Controller + USB Bluetooth dongle (via `PS3BT.h`)

---

## Software Architecture

The main control loop manages:
- PS3 input parsing with debounce logic
- Movement control via `ST->drive()` and `ST->turn()`
- Scene management via millis()-based timers
- Modular functions for each subsystem:
  - `moveMan()`, `moveAuto()`, `routineOneController()`, etc.
  - `playAmbient()`, `startUpSound()`, `drawHyperspaceJump()`, etc.
  - LED FX functions like `TwinkleRandom()`, `redFire()`, `FullCycleThrusterEffect()`

Scene state is tracked using parallel arrays for movement and event timing.

---

## Photos, Videos, and In-Depth Documentation

For more details on the design process, component breakdown, and showcase footage, visit the [project webpage](https://andrewcongdon14.wixsite.com/andrew-congdon/star-tours-ride-vehicle-model).

---

### Main Highlight Reel

[![Watch the Star Tours Ride Vehicle Demo](https://img.youtube.com/vi/Z52RZPWkk8M/0.jpg)](https://www.youtube.com/watch?v=Z52RZPWkk8M)

> *Click the image above to watch the full demo.*

---

### Additional Videos

#### All Automated Routines with Movement  
[![Watch the Automated Routines Video](https://img.youtube.com/vi/Ua834crMiS8/0.jpg)](https://www.youtube.com/watch?v=Ua834crMiS8&t=33s)  
> *Click to view: vehicle movement across all routines.*

#### Nighttime Lighting & Sound Footage  
[![Watch the Nighttime Lighting & Sound Demo](https://img.youtube.com/vi/c_MUbfIIzZo/0.jpg)](https://www.youtube.com/watch?v=c_MUbfIIzZo)  
> *Click to view: synchronized lighting and sound effects in a dark setting.*
      
---

## Files

This repository contains:
- `StarTours.ino` – full Arduino program with all movement logic, LED control, audio syncing, and PS3 input parsing

---
