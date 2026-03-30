#  Experiment 2: Push Button Controlled LED

##  Aim
To interface a push button as a digital input and control an LED by toggling its state on each button press using STM32.

---

##  Components Required
- STM32 Nucleo-F446RE  
- USB Cable  
- STM32CubeIDE  
- STM32CubeMX  

---

##  Theory
GPIO (General Purpose Input/Output) pins in STM32 microcontrollers can be configured as either input or output depending on the application.

In this experiment, pin PC13 is configured as a digital input and is connected to the onboard push button. When the button is pressed, the logic level at the pin changes, which is detected by the microcontroller.

Pin PA5 is configured as a digital output and is connected to the onboard LED. Based on the input from the push button, the LED state is toggled.

A small delay is added to avoid multiple toggles due to mechanical bouncing of the button (debouncing).

---

##  Procedure
1. Open STM32CubeMX  
2. Select STM32F446RE  
3. Configure PA5 as output  
4. Configure PC13 as input  
5. Generate code  
6. Open in STM32CubeIDE  
7. Write toggle logic  
8. Build and run  

---

##  Code
while (1)
{
  if (HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_13) == 0)
  {
    HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_5);
    HAL_Delay(200);
  }
}

---

##  Result
The LED toggles successfully on each button press.

---

##  Learning Outcome
- Understood input-output interfacing  
- Learned push button handling  
- Understood debouncing concept  
- Gained STM32 coding experience  
