# RISC-V Internship Program Powered by SAMSUNG and VSD - 2025 
This is a RISC-V Internship program using VSDSquadron Mini based on RISC-V architecture guided by Mr. Kunal Ghosh, Co-Founder of VSD.

# Basic Details 

**Name:** Purvi G Rao
-
**College:** Sahyadri College of Engineering and Management, Adyar ,Mangaluru
-
**Email ID:** purvi.ec22@sahyadri.edu.in or purvigrao@gmail.com
-
**Github Profile:** Purvi-Rao-Sahyadri_ECE  
-
<details>
<summary>TASK 1: Development of C-Based Lab</summary>
<img 
src="https://github.com/user-attachments/assets/6f272095-eb65-4f4e-afc7-4b5ffa318411" alt="Task Icon"/>
<img
src="https://github.com/user-attachments/assets/caa2b35b-545a-403c-bb3b-7ae22c0f8931" alt="Task Icon"/>
<img
src="https://github.com/user-attachments/assets/8634d13a-b08a-4056-8526-0e7b728d8ac3" alt="Task Icon"/>
<img
src="https://github.com/user-attachments/assets/278e0169-cf09-4077-8afb-e8311fde8cc5" alt="Task Icon"/>
<img
src="https://github.com/user-attachments/assets/002eb4c9-f29d-4066-ab1f-f30b37ca094e" alt="Task Icon"/>
<img
src="https://github.com/user-attachments/assets/40e870ce-ac6a-4f35-98b3-11a03f87642d" alt="Task Icon"/>
</details>
<details>
<summary>TASK 2: Simulation with Spike</summary>
<img 
src="https://github.com/user-attachments/assets/b4d6bcac-d56c-4f7d-a2a3-496d9a473659" alt="Task Icon"/>
<img
src="https://github.com/user-attachments/assets/e957e2a1-f138-4486-b598-1b814a510673" alt="Task Icon"/>
<img
src="https://github.com/user-attachments/assets/96f17a3f-9d16-49fb-a343-74548b3570a6" alt="Task Icon"/>
<img
src="https://github.com/user-attachments/assets/54a309a2-e745-49fb-8786-bd2375f29ed7" alt="Task Icon"/>
</details>
<details>
<summary>TASK 3: Identification of Risc-v instructions</summary>
<img
src="https://github.com/user-attachments/assets/4e90f51f-918e-4300-9d06-3fff9ea543eb" alt="Task Icon"/>
</details>
<details>
 <summary>TASK 4: Functional Simulation of RISC-V core
 </summary>
 <br>
Steps to perform functional simulation of RISCV
 1. Download Files:
Download the code from the reference github repo.

2. Set Up Simulation Environment:
Install iverlog using commands:

        sudo apt install iverilog
        sudo apt install gtkwave

3. To run and simulate the verilog code, enter the following command:

        iverilog -o iiitb_rv32i iiitb_rv32i.v iiitb_rv32i_tb.v
        ./iiitb_rv32i

4. To see the simulation waveform in GTKWave, enter the following command:

        gtkwave iiitb_rv32i.vcd

 <img
 src="https://github.com/user-attachments/assets/bf3a72af-b921-4973-8539-03046100c0b3" alt="Task Icon"/>
<img
 src="https://github.com/user-attachments/assets/9c79aa5c-932f-4027-88f5-fc83e667d391" alt="Task Icon"/>
 <img
 src="https://github.com/user-attachments/assets/cf3abdd1-2287-419b-9f5d-afe4056d3236" alt="Task Icon"/>
 <img
 src="https://github.com/user-attachments/assets/3e2a6bc6-6d04-493d-b96d-42df1d0d50b3" alt="Task Icon"/>
 <img
 src="https://github.com/user-attachments/assets/92ed7467-3390-4574-b59c-a080fd4f03ea" alt="Task Icon"/>
 <img
 src="https://github.com/user-attachments/assets/1b756d38-6116-4ea4-bb38-873afada51bc" alt="Task Icon"/>
 <img
 src="https://github.com/user-attachments/assets/eebff171-fece-4396-9df3-e419c4c67d05" alt="Task Icon"/>
  <img
 src="https://github.com/user-attachments/assets/631b4c68-62cd-4b36-90eb-c0e845dcc584" alt="Task Icon"/>
 <img
 src="https://github.com/user-attachments/assets/82bd15ad-fdb5-475f-9382-0fe30ed88a0a" alt="Task Icon"/>
 <img
 src="https://github.com/user-attachments/assets/eb5cb1d9-7e4b-47aa-bcc2-a6c8ff4c321c" alt="Task Icon"/>
 <img
 src="https://github.com/user-attachments/assets/eadf92f8-3dea-4b23-a4c1-e4db13c383a8" alt="Task Icon"/>
 </details>
 <details>
  
 <summary>TASK 5: Project overview-circuit diagram </summary>
  
 1. PINOUT diagram 
 <img
 src="https://github.com/user-attachments/assets/bb219ef0-06d0-46e5-9bdb-ab9493fabf2a" alt="Task Icon"/>
 
 2.Components Required:
 <img 
 src="https://github.com/user-attachments/assets/70e574a4-a340-4cf2-8833-c55739ca2d41" alt="Task Icon"/>

 <details>
  
 <summary>TASK 6: Project Application </summary>
 
 Code for Half Subtractor:
 ```
 #include<stdio.h>
 #include<debug.h>
 #include<ch32v00x.h>

 // Defining the Logic Gate Functions for the half adder
 int nand(int bit1, int bit2)
 {
    int out= bit1 &&! bit2;
    return out;
 }

 int xor(int bit1, int bit2)
 {
    int out= bit1^bit2;
    return out;
 }

 // Configuring GPIO Pins
 void GPIO_Config(void)
 {
    GPIO_InitTypeDef GPIO_InitStructure = {0}; // Structure variable used for GPIO configuration
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE); // Enable clock for Port D
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOC, ENABLE); // Enable clock for Port C
    
    // Input Pins Configuration: A and B on GPIOD Pin 1 and Pin 2
    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_1 | GPIO_Pin_2;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_IPU; // Defined as Input Type (Pull-Up)
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // Output Pins Configuration: Sum on GPIOC Pin 4 and Carry on GPIOC Pin 5
    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_4 | GPIO_Pin_5;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP; // Defined as Output Type (Push-Pull)
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz; // Defined Speed
    GPIO_Init(GPIOC, &GPIO_InitStructure);
 }

 // Main function to implement the half adder
 int main()
 {
    uint8_t A, B, Difference , Borrow;
    NVIC_PriorityGroupConfig(NVIC_PriorityGroup_1);
    SystemCoreClockUpdate();
    Delay_Init();
    GPIO_Config();

    while(1)
    {
        // Read inputs from GPIO
        A = GPIO_ReadInputDataBit(GPIOD, GPIO_Pin_1);
        B = GPIO_ReadInputDataBit(GPIOD, GPIO_Pin_2);
        
        // Compute the half adder outputs
        Difference = xor(A, B);     // Sum = A XOR B
        Borrow = nand(A, B);   // Carry = A AND B

        /* Output for SUM on GPIOC Pin 4 */
        if(Difference == 0)
        {
            GPIO_WriteBit(GPIOC, GPIO_Pin_4, RESET);
        }
        else
        {
            GPIO_WriteBit(GPIOC, GPIO_Pin_4, SET);
        }

        /* Output for CARRY on GPIOC Pin 5 */
        if(Borrow == 0)
        {
            GPIO_WriteBit(GPIOC, GPIO_Pin_5, RESET);
        }
        else
        {
            GPIO_WriteBit(GPIOC, GPIO_Pin_5, SET);
        }
    }
 }
 


 





 
