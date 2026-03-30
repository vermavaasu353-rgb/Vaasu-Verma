# Experiment 6: FreeRTOS Task Implementation on STM32

## Aim
To develop a basic FreeRTOS-based project on STM32F446RE and validate LED blinking using a single RTOS task.

---

## Components Required
- STM32 Nucleo-F446RE  
- USB Cable  
- STM32CubeIDE  
- STM32CubeMX  

---

## Theory
A Real-Time Operating System (RTOS) such as FreeRTOS replaces the traditional super loop architecture with a scheduler that manages multiple tasks.

Each task has its own stack, priority, and execution state. The scheduler ensures efficient CPU utilization by switching between tasks.

In this experiment, a single task is created using CMSIS-RTOS v2. The task toggles the onboard LED and uses osDelay() to create periodic execution.

Unlike blocking delays, osDelay() only pauses the current task, allowing the CPU to execute other tasks.

---

## Procedure
1. Open STM32CubeMX  
2. Select STM32F446RE  
3. Configure PA5 as GPIO output  
4. Configure system clock  
5. Enable FreeRTOS (CMSIS_V2)  
6. Create Task_1  
7. Generate code  
8. Open in STM32CubeIDE  
9. Configure SWV debugging  
10. Build and run  

---

## Code
void Task1_function(void *argument)
{
  for(;;)
  {
    HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_5);
    printf("Task_1 Executing for LED Toggle\n");
    osDelay(500);
  }
}

---

## Observation
- LED toggled at regular intervals  
- SWV ITM console displayed task messages  
- Timing was consistent and accurate  

---

## Result
A FreeRTOS task was successfully created and executed. LED blinking and SWV output confirmed correct task scheduling.

---

## Learning Outcome
- Learned RTOS fundamentals  
- Understood task scheduling  
- Gained experience with FreeRTOS  
- Learned SWV debugging  

---

## Conclusion
FreeRTOS improves multitasking and system efficiency. It is essential for complex embedded applications requiring precise timing and task management.
