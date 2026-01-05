# Axiom I — Autonomous Product Retriever
### Warehouse Automation Robot for Order Fulfillment

An autonomous robot designed to navigate warehouse environments, identify cargo via barcode scanning, and transport boxes to designated fulfillment areas using a custom forklift mechanism.

---

## Overview

Axiom I is an Autonomous Product Retriever (APR) developed for Buy More's warehouse automation needs. The robot navigates warehouse aisles using coordinate-based mapping, identifies cargo through color-sensor barcode scanning, and transports boxes weighing up to 250g using a retractable forklift system.

**Platform:** LEGO Mindstorms EV3  
**Language:** EV3 Block-Based Programming

---

## Features

| Capability | Implementation |
|------------|----------------|
| **Navigation** | Coordinate-based mapping with gyroscope-assisted positioning |
| **Locomotion** | 4-wheel tank drive for stability and precise turning |
| **Object Detection** | Ultrasonic sensor for obstacle avoidance and box positioning |
| **Identification** | Color sensor for barcode scanning and cargo classification |
| **Transport** | Retractable forklift with rubber grippers (250g+ capacity) |

---

## System Architecture

```
                    ┌─────────────────────────────────────┐
                    │           EV3 Brick                 │
                    │      (Central Controller)           │
                    └──────────────┬──────────────────────┘
                                   │
       ┌───────────────┬───────────┼───────────┬───────────────┐
       │               │           │           │               │
       ▼               ▼           ▼           ▼               ▼
┌─────────────┐ ┌─────────────┐ ┌─────┐ ┌─────────────┐ ┌─────────────┐
│  Gyroscope  │ │ Ultrasonic  │ │Drive│ │   Color     │ │  Forklift   │
│   Sensor    │ │   Sensor    │ │Motors│ │   Sensor    │ │   Motor     │
├─────────────┤ ├─────────────┤ ├─────┤ ├─────────────┤ ├─────────────┤
│ Orientation │ │  Obstacle   │ │ 4WD │ │  Barcode    │ │ Lift/Lower  │
│  Tracking   │ │  Detection  │ │Tank │ │  Scanning   │ │   Cargo     │
└─────────────┘ └─────────────┘ └─────┘ └─────────────┘ └─────────────┘
```

---

## Hardware Components

### Sensors

| Sensor | Location | Function |
|--------|----------|----------|
| Gyroscope | Chassis center | Orientation tracking for accurate turns |
| Ultrasonic | Front-mounted | Obstacle detection & distance measurement |
| Color Sensor | Forklift arm | Barcode scanning for cargo identification |

### Actuators

| Component | Quantity | Function |
|-----------|----------|----------|
| Large Motors | 2 | Tank drive locomotion |
| Medium Motor | 1 | Forklift lift mechanism |

### Chassis Design

- **Drive System:** 4-wheel tank configuration for stability
- **Forklift:** Belt-driven retractable arm with rubber grippers
- **Frame:** Modular LEGO Technic construction

---

## Design Evolution

The project went through three major iterations:

### Prototype 1.0
- 2 wheels + marble rear support
- Issues: Unpredictable positioning, poor turning accuracy

### Prototype 2.0
- Upgraded to 4-wheel tank drive
- Added sensors (gyro, ultrasonic, color)
- Issues: Forklift couldn't lift boxes, poor barcode reading

### Prototype 3.0 (Axiom I)
- Retractable belt-driven forklift
- Repositioned color sensor on moving arm
- Reinforced lifting mechanism
- **Result:** Successfully completed all demo tasks

---

## Functional Capabilities

### Navigation System
The robot uses a coordinate-based mapping system combined with gyroscope feedback for precise movement:

- **Straight-line travel:** Motor encoder-based distance tracking
- **Turning:** Gyroscope-assisted angle measurement
- **Position correction:** Error compensation based on locomotion test data

### Barcode Scanning
The color sensor mounted on the forklift arm scans vertical barcodes on cargo boxes:

- Reads reflected light values to decode barcode patterns
- Identifies cargo type and destination
- 90%+ identification accuracy target

### Material Handling
The forklift system features:

- Belt-driven vertical movement
- Rubber grippers to prevent cargo slippage
- 250g+ lifting capacity
- Controlled lowering for accurate placement

---

## Demo Performance

During the final demonstration, Axiom I completed all subtasks:

| Subtask | Description | Status |
|---------|-------------|--------|
| 1 | Move forward and return to home base | ✅ |
| 2 | Navigate with rotation and return | ✅ |
| 3 | Locate box, scan barcode, transport to Zone A | ✅ |
| 4 | Locate box, scan barcode, transport to Zone B | ✅ |

---

## Testing & Analysis

### Locomotion Test Results

Mathematical models were developed to predict positioning error:

| Test Type | X-Error Model | Y-Error Model |
|-----------|---------------|---------------|
| Straight Line | Linear regression | Linear regression |
| Turning | Linear regression | Linear regression |

Statistical analysis revealed the need for the 4-wheel redesign due to inconsistent marble-based movement.

---

## Project Structure

```
axiom-autonomous-robot/
├── README.md
└── Design_Notebook.pdf
    ├── Project Management
    │   └── Work Breakdown Structure
    ├── Design Process
    │   ├── Morphological Chart
    │   └── Decision Matrix
    ├── Prototype Evolution
    │   ├── Prototype 1.0 (2-wheel + marble)
    │   ├── Prototype 2.0 (4-wheel + sensors)
    │   └── Prototype 3.0 (Axiom I)
    ├── EV3 Code (Block Programs)
    │   ├── Subtask 1a – Forward and Return
    │   ├── Subtask 1b – Forward, Rotate, Return
    │   ├── Subtask 3 & 4 – Full Pickup Sequence
    │   └── Final Code
    ├── Testing & Analysis
    │   ├── Locomotion Test Data
    │   ├── X/Y Error Graphs
    │   └── Statistical Analysis (Mean, Variance, Std Dev)
    └── Demo Results
        └── Final Demonstration Photos
```

---

## Specifications

| Parameter | Value |
|-----------|-------|
| Dimensions | Compact warehouse-aisle compatible |
| Weight Capacity | 250g minimum |
| Drive Type | 4-wheel tank drive |
| Controller | LEGO EV3 Brick |
| Sensors | Gyroscope, Ultrasonic, Color |
| Power | EV3 Rechargeable Battery |

---

## Future Enhancements

1. **Square wheelbase** — Enable true pivot-on-spot turning
2. **Stabilized lift mechanism** — Reduce front-weight drag
3. **Triple wheel per side** — Increase ground contact and torque
4. **Upgraded motors** — Improved speed and lifting power
5. **Enhanced sensors** — Higher accuracy color/distance sensing

---

## Lessons Learned

- **Iterative design is essential** — Three prototypes were needed to achieve reliability
- **Test early and often** — Locomotion testing revealed critical design flaws
- **Sensor placement matters** — Moving the color sensor to the forklift arm solved barcode reading issues
- **Stability over speed** — 4-wheel tank drive sacrificed maneuverability for predictable movement

---

This project was completed as part of academic coursework. Feel free to reference for educational purposes.

## License

This project was completed as part of academic coursework. Feel free to reference for educational purposes.
