# 🦁 Sensor-Based Lion Using E-Waste

## 📌 Project Overview
This project demonstrates a **Sensor-Based Robotic Lion** built using **E-Waste**, designed to simulate lion-like behavior such as object detection, roaring, and tail movement.

Developed as an **educational and environmental innovation**, this project integrates electronics, robotics, and sustainability to promote hands-on learning among engineering students.

---

## 🎯 Features
- Object detection using **ultrasonic sensor** (range: 2 meters)
- Automatic roaring sound when object detected
- Jaw and Tail movement using motor mechanism
- Body made from **recycled e-waste components**

---

## 🧰 Components Used
| Component | Quantity | Purpose |
|----------|----------|---------|
| Arduino Uno | 1 | Main controller |
| Ultrasonic Sensor (HC-SR04) | 1 | Object detection |
| Servo Motor | 1 | Jaw movement|
| Servo Motor | 1 | Tail wagging |
| Speaker Module / Buzzer | 1 | Roaring sound |
| Jumper Wires | As required | Connections |
| Battery Pack | 1 | Power supply |
| E-Waste materials (old toys, plastic parts, etc.) | As required | Lion body & structure |

---

## 🔌 Circuit Diagram
```
Ultrasonic Sensor:
 - VCC → 5V
 - GND → GND
 - Trig → Pin 9
 - Echo → Pin 10

Servo Motor:
 - Signal → Pin 6
 - VCC → 5V
 - GND → GND

Speaker/Buzzer:
 - Signal → Pin 7
 - GND → GND
```

---

## 💻 Arduino Code
```
#include <Servo.h>

Servo tailServo;
int trigPin = 9;
int echoPin = 10;
int buzzer = 7;
int tailPin = 6;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  pinMode(buzzer, OUTPUT);
  tailServo.attach(tailPin);
  Serial.begin(9600);
}

void loop() {
  long duration;
  int distance;

  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  duration = pulseIn(echoPin, HIGH);
  distance = duration * 0.034 / 2;

  Serial.print("Distance: ");
  Serial.println(distance);

  if (distance < 200) {
    digitalWrite(buzzer, HIGH);
    tailServo.write(30);
    delay(500);
    tailServo.write(150);
    delay(500);
    digitalWrite(buzzer, LOW);
  } else {
    tailServo.write(90);
    digitalWrite(buzzer, LOW);
  }
  delay(300);
}
```

---

## 🧑‍🏫 Project Guide
**Mentor:** Pratibha Gahlot  
**Students Involved:** Tushar Garg, Rakesh, Umesh, Vansh, Sonu, Shubham, Mantosh, Vandana  
**Department:** Electronics & Communication Engineering (ECE)  
**College:** Aravali College of Engineering and Management

---

## ♻️ Innovation & Sustainability Note
- Promotes **reuse of discarded electronics**
- Encourages **environment-friendly creativity** in robotics

---

## 📷 Media

https://www.dropbox.com/scl/fi/e46jaub30tsymerp50mbf/20200130_150719.jpg?rlkey=a3gl1t3ijfulqhjonhs750sjc&st=najyicf7&dl=0
- https://www.dropbox.com/scl/fi/y9okq9f15x77q0b94pjn5/20200206_122322.jpg?rlkey=t8v22iucagdcn8b1tt6hhhlzy&st=6d4razsz&dl=0
- https://www.dropbox.com/scl/fi/gr47un28w0dbds0o6pp2q/20200203_134326.jpg?rlkey=cyqwszkpegqtll23rlv8yewg3&st=hrlxu8xq&dl=0
- https://www.dropbox.com/scl/fi/7n6oxugbvvehl1z84krql/20200223_233102.jpg?rlkey=vz16hlvmhhi29b224hd1ewhk8&st=xj2583qb&dl=0
- 
https://www.instagram.com/reel/Crz15qOInrx/?igsh=MWNqbTJzZzExaGxhYw==
---

## 🌐 Repository Details
This project is part of submission to:
- **Elecrow 2nd Electronics Design Contest**
- **DST recognized incubator (direct email submission)**
- **GitHub Repository for global visibility**

---

## 📩 Contact
For any queries or collaboration:
- Email: [pratibha.gahlot2009@gmail.com]
- GitHub:[https://github.com/Prat06-ece/Sensor-Lion-Ewaste]
---

> 🔖 *"Bridging innovation and sustainability through e-waste robotics."*
