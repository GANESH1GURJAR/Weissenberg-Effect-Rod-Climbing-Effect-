# Weissenberg Effect (Rod Climbing Effect)

This project presents the design, development, and experimentation of an apparatus to study the **Weissenberg Effect**, a unique behavior of viscoelastic fluids where the fluid climbs a rotating rod.

## 🧪 Overview

The Weissenberg Effect is observed in non-Newtonian fluids due to elastic normal stresses under shear flow. This setup investigates the rod-climbing phenomenon using a controlled rotation system and Polyacrylamide (PAM) solutions of varying concentrations.

## 🛠️ Experimental Setup

- **Stepper Motor**: NEMA 17
- **Driver**: TB6600
- **Controller**: Arduino Uno
- **RPM Control**: 10kΩ Potentiometer
- **Working Fluid**: PAM solutions (5000, 10000, 15000 ppm)
- **Recording**: High-Speed Camera
- **Beaker + Mild Steel Rod**
- **Magnetic Stirrer**: For homogeneous solution preparation

## ⚙️ Circuit and Code

Arduino controls the motor RPM using potentiometer feedback. Here's a sample code snippet:

```cpp
int potPin = A0;
int stepPin = 3;
int dirPin = 2;
int speedValue;

void setup() {
  pinMode(stepPin, OUTPUT);
  pinMode(dirPin, OUTPUT);
  digitalWrite(dirPin, LOW);
}

void loop() {
  speedValue = analogRead(potPin);
  int delayTime = map(speedValue, 0, 1023, 2000, 50);
  digitalWrite(stepPin, HIGH);
  delayMicroseconds(delayTime);
  digitalWrite(stepPin, LOW);
  delayMicroseconds(delayTime);
}
📊 Observations
No climbing observed with water (Newtonian)

5000 ppm: Minimal effect

10000 ppm: Moderate climbing at higher RPM

15000 ppm: Maximum climbing due to higher elasticity

📈 Results
PAM Concentration	Max Climbing Height	Threshold RPM
5000 ppm	Low	High
10000 ppm	Moderate	Medium
15000 ppm	High	Low

📚 References
A.S. Lodge et al. Rod-climbing in viscoelastic fluids, J. Chem. Phys.

Bird, Armstrong, Hassager - Dynamics of Polymeric Liquids

Weissenberg, K. (1947) - Continuum Theory of Rheology

👨‍🔬 Contributors
Ganesh Gurjar (2022MEB1309)
Department of Mechanical Engineering, IIT Ropar
Project Guide: Dr. Devranjan Samanta
