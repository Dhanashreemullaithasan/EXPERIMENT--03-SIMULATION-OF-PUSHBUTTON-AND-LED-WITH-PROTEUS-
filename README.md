# EXPERIMENT--03-SIMULATION-OF-PUSHBUTTON-AND-LED INTERFACE WITH ARM CONTROLLER AND PROTEUS 
## Aim: To Interface a Digital output (LED) and Digital input (Pushbutton) to ARM development board , and simulate it in Proteus 
## Components required: STM32 CUBE IDE, Proteus 8 simulator .
## Theory 
The full form of an ARM is an advanced reduced instruction set computer (RISC) machine, and it is a 32-bit processor architecture expanded by ARM holdings. The applications of an ARM processor include several microcontrollers as well as processors. The architecture of an ARM processor was licensed by many corporations for designing ARM processor-based SoC products and CPUs. This allows the corporations to manufacture their products using ARM architecture. Likewise, all main semiconductor companies will make ARM-based SOCs such as Samsung, Atmel, TI etc.

What is an ARM7 Processor?
ARM7 processor is commonly used in embedded system applications. Also, it is a balance among classic as well as new-Cortex sequence. This processor is tremendous in finding the resources existing on the internet with excellence documentation offered by NXP Semiconductors. It suits completely for an apprentice to obtain in detail hardware & software design implementation.

  STM32F401xB STM32F401xC ARM® Cortex®-M4 32b MCU+FPU, 105 DMIPS, 256KB Flash/64KB RAM, 11 TIMs, 1 ADC, 11 comm.
interfaces Datasheet - production data Features
• Core: ARM® 32-bit Cortex®-M4 CPU with FPU, Adaptive real-time accelerator (ART Accelerator™) allowing 0-wait state execution from Flash memory, frequency up to 84 MHz, memory protection unit, 105 DMIPS/ 1.
25 DMIPS/MHz (Dhrystone 2.
1), and DSP instructions
• Memories – Up to 256 Kbytes of Flash memory – Up to 64 Kbytes of SRAM
 
 

## Procedure:
 1. click on STM 32 CUBE IDE, the following screen will appear 
 2. click on FILE, click on new stm 32 project 
 3. select the target to be programmed  as shown below and click on next 
 4.select the program name 
 5. corresponding ioc file will be generated automatically 
 6.select the appropriate pins as gipo, in or out, USART or required options and configure 
 7.click on cntrl+S , automaticall C program will be generated 
 8. edit the program and as per required 
 9. use project and build  
 10. once the project is bulild 
 11. click on debug option 
 12.  Creating Proteus project and running the simulation
 We are now at the last part of step by step guide on how to simulate STM32 project in Proteus.
 13. Create a new Proteus project and place STM32F40xx i.e. the same MCU for which the project was created in STM32Cube IDE. 
 14. After creation of the circuit as per requirement as shown below 
 15. Double click on the the MCU part to open settings. Next to the Program File option, give full path to the Hex file generated using STM32Cube IDE. Then set the external crystal frequency to 8M (i.e. 8 MHz). Click OK to save the changes.
16. click on debug and simulate using simulation as shown below 

## STM 32 CUBE PROGRAM :
```
NAME: DHANASHREE M
REGISTER NUMBER:21221230018

#include "main.h"
#include "stdio.h"
#include "stdbool.h"
bool pushbutton;
void SystemClock_Config(void);
static void MX_GPIO_Init(void);
int main(void)
{
  HAL_Init();
  SystemClock_Config();
  MX_GPIO_Init();
  while (1)
  {
	  pushbutton = HAL_GPIO_ReadPin(GPIOA,GPIO_PIN_4);
	  	  if (pushbutton == 0)
	  	    {
	  		  HAL_GPIO_WritePin(GPIOA,GPIO_PIN_5,GPIO_PIN_SET);
	  		  HAL_Delay(250);
	  		  HAL_GPIO_WritePin(GPIOA,GPIO_PIN_5,GPIO_PIN_RESET);
	  		  HAL_Delay(250);
	  	    }
	  	  else
	  		{
	  		  HAL_GPIO_WritePin(GPIOA,GPIO_PIN_5,GPIO_PIN_RESET);
	  		  HAL_Delay(500);
	  		}
  }
}
```


## Output screen shots of proteus  :
### LED OFF:
![led off](https://user-images.githubusercontent.com/94165415/234837764-23253dbc-d043-443a-a16e-c608faa13578.png)

### LED ON:

![WhatsApp Image 2023-04-27 at 16 16 11](https://user-images.githubusercontent.com/94165415/234840417-68736f27-3d1c-4cc3-8913-1cf506dc564d.jpeg)

## Proteus layout(Add pdf screen shot of circuit here)
![WhatsApp Image 2023-04-27 at 16 16 12](https://user-images.githubusercontent.com/94165415/234840435-c6eb7374-3821-4049-b8f9-961e9275a5b0.jpeg)

## Result :
Interfacing a digital output and digital input  with ARM microcontroller are simulated in proteus and the results are verified.


