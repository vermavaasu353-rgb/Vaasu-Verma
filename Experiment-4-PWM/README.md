# Experiment 4: PWM Signal Generation using STM32

## Aim
To generate a PWM signal using a timer on STM32F446RE and control LED brightness by varying duty cycle.

---

## Components Required
- STM32 Nucleo-F446RE  
- USB Cable  
- STM32CubeIDE  
- STM32CubeMX  

---

## Theory
Pulse Width Modulation (PWM) is a digital technique used to control analog devices by varying the duty cycle of a square wave signal.

The duty cycle represents the percentage of time the signal remains HIGH during one complete cycle. A higher duty cycle increases the average voltage, resulting in higher LED brightness.

STM32 microcontrollers include timers capable of generating PWM signals. The timer works using the following registers:
- Prescaler (PSC) to divide clock frequency  
- Auto Reload Register (ARR) to define period  
- Capture Compare Register (CCR) to define duty cycle  

In PWM mode:
- Output is HIGH when counter is less than CCR  
- Output is LOW when counter is greater than or equal to CCR  

---

## Procedure
1. Open STM32CubeMX  
2. Select STM32F446RE  
3. Configure PA5 as TIM2 channel  
4. Set timer parameters (PSC, ARR)  
5. Generate code  
6. Open project in STM32CubeIDE  
7. Write PWM control logic  
8. Build and run  

---

## Code
HAL_TIM_PWM_Start(&htim2, TIM_CHANNEL_1);

while (1)
{
  for(int x = 0; x < 1000; x++)
  {
    __HAL_TIM_SET_COMPARE(&htim2, TIM_CHANNEL_1, x);
    HAL_Delay(1);
  }

  for(int x = 1000; x > 0; x--)
  {
    __HAL_TIM_SET_COMPARE(&htim2, TIM_CHANNEL_1, x);
    HAL_Delay(1);
  }
}

---

## Observation

| CCR Value | Duty Cycle (%) | Brightness Level |
|----------|----------------|------------------|
| 0        | 0              | OFF              |
| 250      | 25             | Low              |
| 500      | 50             | Medium           |
| 750      | 75             | High             |
| 1000     | 100            | Maximum          |

---

## Result
PWM signal was successfully generated and LED brightness was controlled by varying duty cycle.

---

## Learning Outcome
- Learned PWM generation using timers  
- Understood duty cycle concept  
- Gained practical embedded programming experience  

---

## Conclusion
This experiment demonstrated the use of PWM for controlling LED brightness using STM32 timers, which is an important concept in embedded systems.
