#  Team Techno Dynamics 

##  Overview
This repository documents the design, implementation, and algorithms for **Team Techno Dynamics**’ autonomous mobile robot, developed for the **Hawkins Interdimensional Challenge**.

The challenge simulates a high-stakes mission to seal an interdimensional rift, with the robot completing **8 sequential tasks** involving navigation, object manipulation, color tracking, portal traversal, and precision coin placement — all autonomously.

---

##  Project Goals
- Complete all **8 game tasks** within the given arena and time constraints.
- Achieve **high accuracy** in line/color following, maze navigation, and box manipulation.
- Ensure **robust obstacle avoidance** and reliable performance over varying terrains.
- Integrate mechanical, electronic, and software subsystems seamlessly.

---

##  Key Features

### **Sensors**
- **IR Sensor Array (Raykha S8 – TCRT5000)** – White/dashed line following, barcode reading.
- **VL53L5x Time-of-Flight Sensors** – Wall following & box height measurement.
- **TCS34725 Color Sensor** – Color line detection (Red/Blue).
- **Ultrasonic Sensor** – Portal open/close detection.
- **Magnetometer** – Coin drop trigger detection.

### **Actuators**
- **JGB37-520 DC Motors** – High torque for mobility.
- **Servo Motors** – For grabber, lifting mechanism, and coin-drop control.

### **Power Supply**
- **3 × 3.7V Li-ion Batteries** – 11.1V total for extended runtime.

---

## Task Breakdown
1. **Barcode Reading & White Line Following**  
   - Detect line width to generate binary code.  
   - Apply PID control for accurate tracking.
   
2. **Maze Navigation & Box Manipulation**  
   - Pick up/release virtual box with movement restrictions.
   
3. **Color Line Following**  
   - Follow assigned color (Red/Blue) based on Task 2 outcome.  
   - PD control for smooth tracking.

4. **Dashed Line Navigation**  
   - Handle intermittent line patterns using IR array.

5. **Portal Navigation**  
   - Time movement with a periodically opening gate.  
   - Switch line colors post-portal.

6. **Box Arrangement**  
   - Sort boxes in ascending/descending height order depending on color path.

7. **Hidden Task & Chamber Insertion**  
   - Insert small box into chamber after completing secret challenge.

8. **Uneven Terrain & Coin Drop**  
   - Navigate stacked platforms.  
   - Drop coin at precise magnetized location to trigger light.

---

##  Control Algorithms
- **Line Following:** PID-based correction from IR sensor data.
- **Wall Following:** Distance-based motor speed adjustment from ToF readings.
- **Color Line Following:** PD control with TCS34725 + IR sensor data fusion.
- **Portal Timing:** Ultrasonic sensor-based detection and gate sync.
- **Gripper & Lift Control:** Servo-based precise movement sequences.
- **Coin Drop Logic:** Magnetometer-triggered servo actuation.

---

##  Mechanical Design
- **Chassis:** Custom design to fit max 250mm × 250mm footprint.
- **Mechanisms:** Rack & pinion lift, servo-actuated grabber, coin holder.
- **Durability:** Capable of stable movement on uneven terrain.

---

