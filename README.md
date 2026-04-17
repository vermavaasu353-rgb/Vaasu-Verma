# RTOS Lab Repository

## Student Details
Name: Vaasu Verma  
Course: Real-Time Operating Systems Lab  
Roll No: 2410994604
---

## About This Repository
This repository contains laboratory experiments performed as part of the RTOS course. The experiments are implemented using the STM32 Nucleo-F446RE microcontroller and demonstrate fundamental concepts of embedded systems and real-time processing.

The repository is structured in an organized manner with proper documentation including theory, procedure, code, and results. It reflects both conceptual understanding and practical implementation of embedded system design.

---

## Objective
The main objectives of this repository are:
- To understand embedded system fundamentals  
- To implement GPIO-based input and output operations  
- To gain hands-on experience with STM32 microcontrollers  
- To learn real-time system concepts  
- To develop structured documentation and coding practices  

---

## Experiments Included

### Experiment 1: GPIO LED Control
- Configured GPIO pin as output  
- Controlled onboard LED  
- Learned digital output operation  

### Experiment 2: Push Button Controlled LED
- Interfaced push button as input  
- Implemented LED toggling  
- Understood debouncing concept  

### Experiment 3: Ultrasonic Sensor Interfacing
- Measured distance using HC-SR04 sensor  
- Used timer for time-of-flight calculation  
- Implemented LED indication  

### Experiment 4: PWM Signal Generation
- Generated PWM signal using timer  
- Controlled LED brightness  
- Understood duty cycle concept  

---
###  Experiment 5: Super Loop Based System
- Implement infinite loop architecture  
- Perform multiple tasks (LED + Button + Sensor)  
- Use software counters for scheduling  
- Learn cooperative multitasking  

---

###  Experiment 6: FreeRTOS Task Implementation
- Integrate FreeRTOS  
- Create and manage tasks  
- Use scheduler for multitasking  
- Non-blocking delays using `osDelay()`

### Experiment 7: FreeRTOS Task Priority
- Create multiple tasks with different priorities  
- Analyze effect of priority on task execution  
- Observe LED behavior under different priorities  
- Understand preemptive scheduling in RTOS  

---

### Experiment 8: Semaphore with Interrupt (EXTI)
- Configure external interrupt using push button  
- Implement binary semaphore for synchronization  
- Trigger task execution using ISR  
- Understand event-driven task execution  

---

### Experiment 9: Queue Communication (Producer-Consumer)
- Implement inter-task communication using queue  
- Create producer and consumer tasks  
- Transfer data safely between tasks  
- Understand FIFO and thread-safe communication

---
## Tools and Technologies Used
- STM32 Nucleo-F446RE  
- STM32CubeIDE  
- STM32CubeMX  
- Embedded C Programming  

---

## Key Concepts Covered
- GPIO Configuration  
- Digital Input and Output  
- Timer Programming  
- PWM Signal Generation  
- Sensor Interfacing  
- Real-Time Concepts  

---

## Repository Structure

```
RTOS-Lab/
│
├── 📁 Experiment-1-GPIO-LED/
├── 📁 Experiment-2-Push-Button/
├── 📁 Experiment-3-Ultrasonic-Sensor/
├── 📁 Experiment-4-PWM/
├── 📁 Experiment-5-Super-Loop/
├── 📁 Experiment-6-FreeRTOS/
├── 📁 Experiment-7-Task-Priority/
├── 📁 Experiment-8-Semaphore-Interrupt/
├── 📁 Experiment-9-Queue-Communication/
│
└── 📄 README.md
```


## Learning Outcomes
- Understanding of embedded system design  
- Practical knowledge of microcontroller programming  
- Ability to interface sensors and actuators  
- Improved debugging and coding skills  
- Exposure to real-time system concepts  

---

## Future Scope
- Implementation of FreeRTOS  
- Multitasking applications  
- Interrupt-based systems  
- Advanced embedded projects  

---

## Conclusion
This repository represents a structured approach to learning RTOS and embedded systems using STM32. It provides a strong foundation for developing real-world applications in embedded engineering.
