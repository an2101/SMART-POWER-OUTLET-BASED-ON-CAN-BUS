**This is midterm project about "SMART POWER OUTLET BASED ON CAN BUS" in Real-time Systems course**. Details information midterm project, please access in Folder "Document/Slide_RTOS_midterm_report.pptx"  
Demo video: https://drive.google.com/file/d/1uJZdLKMzb7t7uUvIZkhNDOHja9ycd7Sn/view?usp=drive_link  
**Walkthrough:**  
**1. Connect the devices according to the following diagram.**  
![Circuit](Document/circuit.png)  
**2. Install Arduino IDE and STM32CubeIDE (skip if installed)**  
Link Arduino IDE: https://www.arduino.cc/en/software  
Linh STM32CubeIDE: https://www.st.com/en/development-tools/stm32cubeide.html  
**3. Load program on Esp32-C3**  
Open Arduino IDE, open File/Preferences..., copy this link to manager URL: https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json (ignore if done)  
![Circuit](img_source/arduino1.png)  
Install esp32 board (ignore if done)  
![Circuit](img_source/arduino2.png)  
Connect Esp32-c3 to your computer. Then select board and port.  
![Circuit](img_source/arduino3.png)  
Load program on Esp32-c3, source code in "esp32.ino" file  
![Circuit](img_source/arduino4.png)  
**4. Load program on STM32**  
Open STM32CubeIDE, creat STM32 project, select board (STM32F103C6T6), select Location project.  
![Circuit](img_source/stm1.png)  
**STM32CubeIDE Settings on STM32 1st**  
Click System Core/sys/select debug "Serial Wire" and select Timebase Source "TIM3"  
Click RCC → High Speed Clock (HSE) to Crystal/Ceramic Resonator  
Click Clock Configuration tab → HCLK (MHz) to 72  
Click PB3 GPIO and Configuration Output state.  
Click connectivity --> Click CAN --> Mode --> Activated  
Parameter Settings --> Prescalor 72 & Time Quanta in Bit Segment1 - 2 Times (Baud 125000)  
Set PB9 to CAN_TX (PB8 will auto set to CAN_RX)  
Click Middleware and Software Packs/FREERTOS/select interface "CMSIS_V1"  
Click connectivity --> Click USART1 --> Mode --> Asynchronous  
![Circuit](img_source/stm2.png)  
**STM32CubeIDE Settings on STM32 2nd**  
Click System Core/sys/select debug "Serial Wire" and select Timebase Source "TIM3"  
Click RCC → High Speed Clock (HSE) to Crystal/Ceramic Resonator  
Click Clock Configuration tab → HCLK (MHz) to 72  
Click PB3 GPIO and Configuration Output state.  
Click connectivity --> Click CAN --> Mode --> Activated  
Parameter Settings --> Prescalor 72 & Time Quanta in Bit Segment1 - 2 Times (Baud 125000)  
Set PB9 to CAN_TX (PB8 will auto set to CAN_RX)  
Click Middleware and Software Packs/FREERTOS/select interface "CMSIS_V1"  
![Circuit](img_source/stm3.png)  
Code will be generate after save the setting. Copy the code in main.c (rtos_stm32_1 and rtos_stm32_2) on your project.  
Finally, load program on stm32 1st and 2nd with ST-LINK/V2.
