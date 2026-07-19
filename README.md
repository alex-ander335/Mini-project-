# Smart Device Management System[span_0](start_span)[span_0](end_span)

This repository contains a terminal-based **Smart Device Management System** developed as part of the **EL 162 / 234 Object Oriented Programming** course[span_1](start_span)[span_1](end_span). It simulates a home automation setup where users can monitor and control various devices[span_2](start_span)[span_2](end_span).

## Project Details
* **Course:** EL 162 / 234 Object Oriented Programming[span_3](start_span)[span_3](end_span)
* **Instructor:** Dr. Matthew Cobbinah[span_4](start_span)[span_4](end_span)
* **Author:** Alex[span_5](start_span)[span_5](end_span)

---

## OOP Concepts Demonstrated[span_6](start_span)[span_6](end_span)
* **Encapsulation:** Attributes like `__device_id`, `__power_status`, `__brightness`, and `__recording_status` use private double underscores[span_7](start_span)[span_7](end_span). They are safely accessed and modified via Python properties (`@property` getters/setters) to handle data validation[span_8](start_span)[span_8](end_span).
* **Inheritance:** `TemperatureSensor`, `SmartLight`, and `SecurityCamera` act as child classes that inherit foundational attributes and behavior from the `SmartDevice` parent class[span_9](start_span)[span_9](end_span).
* **Polymorphism:** The `SecurityCamera` class overrides the parent class's `display_info()` method to add custom camera-specific state readouts alongside the base metadata[span_10](start_span)[span_10](end_span).

---

## Class Architecture[span_11](start_span)[span_11](end_span)

### 1. `SmartDevice` (Parent Class)[span_12](start_span)[span_12](end_span)
Manages basic device identity and core power functions[span_13](start_span)[span_13](end_span).
* **Attributes:** `name`, `__device_id`, `__power_status`[span_14](start_span)[span_14](end_span)
* **Methods:** `turn_on()`, `turn_off()`, `display_info()`[span_15](start_span)[span_15](end_span)

### 2. `TemperatureSensor` (Child Class)[span_16](start_span)[span_16](end_span)
Monitors environmental temperatures[span_17](start_span)[span_17](end_span).
* **Attributes:** `temperature`[span_18](start_span)[span_18](end_span)
* **Methods:** `read_temperature()` (Blocks operation if the device power is OFF)[span_19](start_span)[span_19](end_span)

### 3. `SmartLight` (Child Class)[span_20](start_span)[span_20](end_span)
Simulates a dimmable smart light fixture[span_21](start_span)[span_21](end_span).
* **Attributes:** `__brightness`[span_22](start_span)[span_22](end_span)
* **Methods:** `increase_brightness()`, `decrease_brightness()` (Caps values safely between 0% and 100%)[span_23](start_span)[span_23](end_span)

### 4. `SecurityCamera` (Child Class)[span_24](start_span)[span_24](end_span)
Handles network video capture capabilities[span_25](start_span)[span_25](end_span).
* **Attributes:** `__recording_status`[span_26](start_span)[span_26](end_span)
* **Methods:** `start_recording()`, `stop_recording()`, `display_info()`[span_27](start_span)[span_27](end_span)

---

## Interactive CLI Menu[span_28](start_span)[span_28](end_span)
The application runs a continuous command-line loop offering the following controls:
1. **Display Device Information:** Prints out a comprehensive status summary for all instantiated devices[span_29](start_span)[span_29](end_span).
2. **Turn Device On:** Switches a chosen device's power status to ON[span_30](start_span)[span_30](end_span).
3. **Turn Device Off:** Switches a chosen device's power status to OFF[span_31](start_span)[span_31](end_span).
4. **Read Temperature:** Pulls the current reading from the `TemperatureSensor` instance[span_32](start_span)[span_32](end_span).
5. **Adjust Brightness:** Launches a sub-menu to step the `SmartLight` brightness up or down by 10%[span_33](start_span)[span_33](end_span).
6. **Start / Stop Recording:** Directly toggles the video capture sequence for the `SecurityCamera`[span_34](start_span)[span_34](end_span).
7. **Exit:** Quits the client application loop safely[span_35](start_span)[span_35](end_span).

---

## How To Run
1. Ensure you have **Python 3.x** installed on your machine
2. Save the script locally as `smart_device_management.py.
3. Open your terminal, navigate to the directory, and run:
   ```bash
   python smart_device_management.py
