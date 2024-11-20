# STM32 FreeRTOS LED Control with Shared Data Simulation  

This project demonstrates the use of **FreeRTOS** on an STM32 microcontroller to control multiple LEDs with tasks and simulate shared data access.  

## Features  
- **Task-based LED Control**  
  - Green LED blinks with a 500 ms delay.  
  - Red LED blinks with a 100 ms delay.  
- **Shared Data Access Simulation**  
  - Tasks share a flag (`startFlag`) to simulate a shared resource.  
  - If a conflict occurs (simultaneous access), the Blue LED lights up as an interference indicator.  
- **FreeRTOS Integration**  
  - Demonstrates multithreading and priority-based task scheduling.  

## Components Used  
- **Hardware**  
  - STM32 Microcontroller (configured for HSI clock source).  
  - Three LEDs connected to GPIO pins:  
    - Green LED: `GPIO_PIN_0`.  
    - Red LED: `GPIO_PIN_1`.  
    - Blue LED: `GPIO_PIN_2`.  
- **Software**  
  - STM32CubeIDE for development and debugging.  
  - FreeRTOS for real-time task management.  

## How It Works  
1. **Task Descriptions**  
   - `GreenLEDTask`: Controls the Green LED, toggling every 500 ms.  
   - `RedLEDTask`: Controls the Red LED, toggling every 100 ms.  
   - Both tasks call `accessSharedData()` to simulate shared resource access.  
2. **Shared Data Handling**  
   - A global variable `startFlag` is used to track data access.  
   - If a task tries to access data while another task is using it, the Blue LED lights up to indicate interference.  

## Setup  
1. Clone this repository:  
   ```bash  
   git clone https://github.com/username/repo-name.git  
