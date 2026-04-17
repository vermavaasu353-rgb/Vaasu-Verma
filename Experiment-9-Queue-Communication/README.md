# Experiment 9: Queue Communication (Producer-Consumer)

## Aim
To implement inter-task communication using a FreeRTOS queue where one task generates data and another task receives and processes it.

---

## Apparatus
- STM32 Nucleo-F446RE Development Board  
- Ultrasonic Sensor (or simulated data)  
- USB Cable  
- STM32CubeIDE  
- STM32CubeMX  

---

## Theory
FreeRTOS queue is used for safe data transfer between tasks.

- Queue follows FIFO (First In First Out) principle  
- It is thread-safe (no data corruption)  
- Supports blocking mechanism  

Concept:
- Producer task generates data  
- Consumer task receives data  
- Queue acts as a buffer between them  

Advantages:
- No shared variable issues  
- Prevents race conditions  
- Efficient synchronization  

---

## Procedure
1. Open STM32CubeMX and create a new project  
2. Select STM32F446RE microcontroller  
3. Enable FreeRTOS (CMSIS_V2)  
4. Create two tasks (Producer and Consumer)  
5. Add a message queue  
6. Configure queue size and data type  
7. Generate code and open in STM32CubeIDE  
8. Write logic for sending and receiving data  
9. Build and flash the code  
10. Observe output using SWV ITM console  

---

## Code Logic
- Producer task sends data to queue  
- Consumer task receives data from queue  
- Blocking ensures synchronization  

```c
void Sensor_Read(void *argument)
{
  unsigned int dist = 0;

  for(;;)
  {
    dist = dist + 1;
    printf("Producer Task\n");
    osMessageQueuePut(myQueue01Handle, &dist, 0, osWaitForever);
    osDelay(1000);
  }
}

void Motion_Control(void *argument)
{
  unsigned int distance;

  for(;;)
  {
    osMessageQueueGet(myQueue01Handle, &distance, NULL, osWaitForever);
    printf("Consumer Task: Distance = %u\n", distance);
  }
}
