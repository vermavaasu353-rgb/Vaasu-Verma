# 📘 Experiment 3: Ultrasonic Sensor Interfacing with STM32

##  Aim
To interface an HC-SR04 ultrasonic sensor with STM32F446RE and measure distance using time-of-flight principle with LED indication.

---

##  Components Required
- STM32 Nucleo-F446RE  
- HC-SR04 Ultrasonic Sensor  
- Jumper Wires  
- USB Cable  
- STM32CubeIDE  
- STM32CubeMX  

---

##  Theory
STM32F446RE microcontroller provides multiple GPIO pins that can be configured as input or output depending on the requirement.

In this experiment, the HC-SR04 ultrasonic sensor is interfaced with STM32 to measure distance using ultrasonic waves. The sensor works on the time-of-flight principle.

A trigger pulse of 10 microseconds is sent from the microcontroller to the sensor. The sensor then emits ultrasonic waves, which travel through air and reflect back after hitting an object.

The Echo pin generates a pulse whose duration represents the time taken for the wave to travel to the object and back.

Using a timer, this time is measured and distance is calculated using:

Distance = (Velocity × Time) / 2

Where velocity of sound ≈ 343 m/s.

---

##  Procedure
1. Open STM32CubeMX  
2. Select STM32F446RE  
3. Configure:
   - PA5 as LED output  
   - TRIG pin as output  
   - ECHO pin as input  
4. Enable Timer (TIM) for microsecond delay  
5. Set prescaler for accurate timing  
6. Generate code  
7. Open project in STM32CubeIDE  
8. Write logic for trigger pulse and echo measurement  
9. Build and run  

---

##  Code (Main Logic)
while (1)
{
  HAL_Delay(3000);
  timep = TIM2->CCR2;
  dist = (timep * 0.0343f) / 2.0f;

  TIM2->SR = TIM2->SR & 0xFB;
  TIM2->CR1 = TIM2->CR1 | 0x01;
}

---

##  Observation

| Distance (Actual cm) | Measured (cm) | LED Status | Remarks |
|--------------------|--------------|-----------|--------|
| 5                  | 5.1          | ON        | Accurate |
| 10                 | 9.8          | ON        | Minor error |
| 15                 | 15.2         | ON        | Stable |
| 20                 | 19.7         | OFF       | Threshold crossed |
| 25                 | 24.9         | OFF       | Accurate |

---

##  Result
The ultrasonic sensor was successfully interfaced with STM32F446RE and distance was measured accurately. The LED provided visual indication based on the distance threshold.

---

##  Learning Outcome
- Learned ultrasonic sensor interfacing  
- Understood time-of-flight measurement  
- Gained knowledge of timer usage in STM32  
- Improved embedded programming skills  

---

##  Conclusion
This experiment demonstrated how ultrasonic sensors can be used for distance measurement in embedded systems. It provides a foundation for applications like obstacle detection and automation systems.

---

##  Applications
- Obstacle detection systems  
- Robotics  
- Distance measurement devices  
- Automation systems  
