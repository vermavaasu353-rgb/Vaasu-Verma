# Experiment 8: Semaphore with Interrupt (EXTI)

## Aim
To configure an external interrupt (EXTI) for a user button and use a binary semaphore to synchronize an LED control task.

---

## Apparatus
- STM32 Nucleo-F446RE Development Board  
- Push Button  
- USB Cable  
- STM32CubeIDE  
- STM32CubeMX  

---

## Theory
This experiment demonstrates the concept of deferred interrupt processing in RTOS.

- Interrupt Service Routines (ISR) should be short and fast  
- Time-consuming operations are handled by tasks  
- A binary semaphore is used for synchronization between ISR and task  

Working principle:
- ISR acts as a producer (gives semaphore)  
- Task acts as a consumer (takes semaphore)  
- Task executes only when triggered by interrupt  

---

## Procedure
1. Open STM32CubeMX and create a new project  
2. Select STM32F446RE microcontroller  
3. Configure PA5 as GPIO output (LED)  
4. Configure PC13 as external interrupt input  
5. Enable EXTI interrupt (falling edge trigger)  
6. Enable FreeRTOS (CMSIS_V2)  
7. Create a task (LED_Control)  
8. Add a binary semaphore  
9. Generate code and open in STM32CubeIDE  
10. Write task and ISR logic  
11. Build and flash the code  
12. Observe output using SWV ITM console  

---

## Code Logic
- Task waits for semaphore  
- ISR releases semaphore when button is pressed  
- Task toggles LED multiple times  

```c
void StartDefaultTask(void *argument)
{
  for(;;)
  {
    if(osSemaphoreAcquire(myBinarySem01Handle, osWaitForever) == osOK)
    {
      for(int i = 0; i < 5; i++)
      {
        HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_5);
        osDelay(250);
      }
      printf("LED Task Executed\n");
    }
  }
}

void HAL_GPIO_EXTI_Callback(uint16_t GPIO_Pin)
{
  if(GPIO_Pin == GPIO_PIN_13)
  {
    osSemaphoreRelease(myBinarySem01Handle);
  }
}
