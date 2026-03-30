# 📘 Experiment 1: GPIO LED Control

##  Aim
To configure a GPIO pin as output and control an onboard LED using STM32.

---

##  Components Required
- STM32 Nucleo-F446RE
- USB Cable
- STM32CubeIDE
- STM32CubeMX

---

##  Theory
GPIO (General Purpose Input/Output) pins in STM32 microcontrollers are versatile pins that can be configured either as input or output based on application requirements.

In this experiment, pin PA5 is configured as a digital output pin and is internally connected to the onboard LED on the STM32 Nucleo-F446RE board. When the microcontroller sets the pin to HIGH (logic 1), current flows through the LED and it glows. When the pin is set to LOW (logic 0), the LED turns OFF.

The GPIO configuration is done using STM32CubeMX, which simplifies hardware setup by generating initialization code. The LED control is implemented in STM32CubeIDE using HAL (Hardware Abstraction Layer) functions such as HAL_GPIO_WritePin().

This experiment helps in understanding basic digital output operation and how a microcontroller interacts with external hardware components.

---

##  Procedure
1. Open STM32CubeMX
2. Select STM32F446RE
3. Configure PA5 as output
4. Generate code
5. Open in STM32CubeIDE
6. Write LED control logic
7. Build and run

---

##  Code
HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);

---

##  Result
The LED successfully turns ON when the pin is set HIGH and turns OFF when set LOW.

---

##  Learning Outcome
- Learned GPIO configuration
- Understood output control
- Gained experience with STM32 tools
