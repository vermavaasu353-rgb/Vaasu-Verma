# Experiment 7: FreeRTOS Task Priority

## Aim
To create and execute two FreeRTOS tasks with different priorities and analyze their effect on LED blinking behavior.

---

## Apparatus
- STM32 Nucleo-F446RE Development Board  
- LED  
- Breadboard and Connecting Wires  
- USB Cable  
- STM32CubeIDE  
- STM32CubeMX  

---

## Theory
FreeRTOS uses preemptive priority-based scheduling, where higher priority tasks execute before lower priority tasks.

- Higher priority → executes immediately  
- Lower priority → gets less CPU time  
- Equal priority → round-robin scheduling  

This experiment demonstrates how task priority affects execution and system performance.

---

## Procedure
1. Open STM32CubeMX and create a new project  
2. Select STM32F446RE microcontroller  
3. Configure GPIO pins (PA5, PA6 as output)  
4. Enable FreeRTOS (CMSIS_V2)  
5. Create two tasks (LED_1 and LED_2)  
6. Assign different priorities  
7. Generate code and open in STM32CubeIDE  
8. Write logic for LED toggling  
9. Build and flash the code  
10. Observe output using SWV ITM console  

---

## Code Logic
- Two tasks are created  
- Each task toggles an LED  
- Delay of 500 ms is used  
- Messages printed using SWV  

```c
void Task1_function(void *argument)
{
  for(;;)
  {
    HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_5);
    printf("Task 1 Running\n");
    osDelay(500);
  }
}

void Task2_function(void *argument)
{
  for(;;)
  {
    HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_6);
    printf("Task 2 Running\n");
    osDelay(500);
  }
}
