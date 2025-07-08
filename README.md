## VSDSquadron Mini RISC-V Internship  

This is based on RISC-V architecture and we use all open source available, where I’m gaining hands-on experience with **RISC-V architecture, chip design, and industry-standard VLSI workflows**. Instructed by Kunal Ghosh sir.


# About Me  

- **Name:** B Keerthi  
- **College:** Ballari Institute of Technology and Management  
- **Email:** bkeerthi975@gmail.com  
- **GitHub:** https://github.com/BKeerthi975  
- **LinkedIn:** https://www.linkedin.com/in/b-keerthi-245449332/

<details>
<summary><strong>Task 1:</strong> Task is to install RISC-V toolchain from provided vdi and perform lab using C program and RISC-V lab</summary>

### 1. Install RISC-V toolchain using vdi file provided
![file-list](https://github.com/user-attachments/assets/fa9673e4-13b9-4bcd-9cbc-4933813ff5da)

### 2. C Program based lab
we have to follow these steps given below to perform this lab
1. Open the terminal and then open leafpad which is editor to save a c program file with name sum1ton
```bash
leafpad sum1ton.c
```
2.Write the c program to add n numbers and then save (crtl+s) 
3.Run the given commend
```bash
gcc sum1ton.c
./a.out
```
![WhatsApp Image 2025-03-24 at 23 13 36 (1)](https://github.com/user-attachments/assets/d7018c2e-c65c-4be1-b009-92a6de2c0389)
![image](https://github.com/user-attachments/assets/40dd2e03-0984-498a-80ec-a0d92f2d749d)

### 3. RISC-V Lab
Follow these commends
1.open terminal and run commend
```bash
cat sum1ton.c
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
ls ltr sum1ton.o
```
![image](https://github.com/user-attachments/assets/c0fc1d31-9ac2-4ccc-a2fb-94486114a7da)

2.run the given commend to see assembly language code of our c program

```bash
riscv64-unknown-elf-objdump -d sum1ton.o
```
![image](https://github.com/user-attachments/assets/cdaf76a8-f9c4-4a11-b6ff-ee30c73282b5)

### 🔍 Explanation of Command-Line 

- **`-mabi=lp64`**:  
  This option sets the Application Binary Interface (ABI) to `lp64`. In this mode, all integers, long integers, and pointers are treated as 64-bit values. It’s the standard ABI used when targeting a 64-bit RISC-V architecture.

- **`-march=rv64i`**:  
  With this flag, the compiler is told to use the `rv64i` instruction set, which is the base 64-bit integer instruction set for RISC-V. It clearly specifies that the code is meant for a 64-bit processor.

- **`riscv-objdump`**:  
  This is a disassembler tool specifically for RISC-V binaries. It helps break down compiled code into assembly instructions, which is very useful for understanding how your code behaves at the hardware level and for debugging.

- **`-Ofast`**:  
  This optimization flag enables aggressive compiler optimizations to boost performance. It goes beyond standard optimization levels by enabling flags that may disregard strict compliance with language standards. It’s ideal for performance-critical applications, but should be used with care since it might cause unexpected behavior in some cases.

- **`-O1`**:  
  This is a basic optimization level. It balances better performance with shorter compilation times. Compared to `-Ofast`, it’s more conservative, aiming to reduce execution time and code size without introducing risks of aggressive transformations.

</details>

<details>
<summary><strong>Task 2:</strong> Task is to perform SPIKE Simulation and Compile C program code and generate RISC-V objdump for both -O1 and -Ofast</summary>
1.WHAT IS SPIKE IN RISC-V?
        
SPIKE is a simulator for the RISC-V Instruction Set Architecture (ISA). It allows developers to test and analyze RISC-V programs without needing real hardware. SPIKE is written in C++ and is open-source. It simulates a RISC-V processor along with its cache system, making it useful for running software like applications or even the Linux kernel. It's commonly used as a starting point for testing and running programs on RISC-V platforms.

2.Install SPIKE

Using below commends we can install Spike 
```bash
sudo apt update
sudo apt install spike 
```

3.Written a c program for product of 2 numbers using the below commend and save it 
```bash
leafpad productab.c &
```
![image](https://github.com/user-attachments/assets/8249f7a7-2bca-4930-a1f0-d97f8a6601e3)

4.Images showing RISC-V objdunp for -O1 and -Ofast 

For -O1 
![image](https://github.com/user-attachments/assets/46579fba-b194-4021-8a1a-19beb9504db7)

For -Ofast
![image](https://github.com/user-attachments/assets/09e9f7cd-d0d4-4afa-b543-e6295d3561a0)

5.Images having 15 instruction for -O1 and 12 for -Ofast

For -O1 getting below shown 
![image](https://github.com/user-attachments/assets/c3354d96-3cbb-4ca4-b755-8a956a5b2e0a)

For -Ofast getting below shown
![image](https://github.com/user-attachments/assets/e4b80a86-579b-497d-9509-18c291310f50)


</details>


<details>
<summary><strong>Task 3:</strong> Task is to decode RISC-V 15 instructions and extract 32-bit code for each</summary>
1.What is RISC-V?

RISC-V is an open-source instruction set architecture (ISA) that empowers developers to design and build processors tailored to specific applications—without the burden of licensing fees. It stands out from proprietary ISAs by offering a flexible and free alternative, making it a popular choice for academic research, startups, and large-scale industrial designs alike.

Rooted in the principles of Reduced Instruction Set Computing (RISC), RISC-V represents the fifth generation of this streamlined computing architecture. Its simplicity and modular design make it both powerful and efficient, ideal for modern computing needs—from embedded systems to supercomputers.


2. Instruction Format in RISC-V

In any processor architecture, the instruction format defines how a machine-level instruction is structured. In RISC-V, instructions are represented in binary (a sequence of 0s and 1s) and each part of the instruction carries specific information—such as what operation to perform, which registers to use, and how data should be processed or moved.

These formats play a critical role in how the processor decodes and executes each command. Understanding how instructions are laid out helps in designing compilers, writing assembly programs, and even building custom hardware that supports the RISC-V standard.

There are 6 instruction formats in RISC-V:

R-format
I-format
S-format
B-format
U-format
J-format
RISCV Instruction Types

Let’s discuss each of the instruction formats in detail with examples.

1. R-type Instruction

In RV32, each instruction is of size 32 bits. In R-type instruction, R stands for register which means that operations are carried on the Registers and not on memory location. This instruction type is used to execute various arithmetic and logical operations. The entire 32 bits instruction is divided into 6 fields as shown below.

R-type

The first field in the instruction format is known as opcode, also referred as operation code. The opcode is of length 7 bits and is used to determine the type of instruction format.
The next subfield is known as rd field which is referred as Destination Register. The rd field is of length 5 bits and is used to store the final result of operation.
The next subfield is func3 also referred as function 3. Here the ‘3’ represents the size of this field. This field tells the detail about the operation, i.e., the type of arithmetic and logical that is performed.
The next two subfields are the source registers, rs1 and rs2 each of length 5 bits. These are mainly used to store and manipulate the data during the execution of instructions.
The last subfield is func7 also referred as function 7. Here ‘7’ represents the size of the field. The function of func7 field is same as that of func3 field.

2. I-type Instruction
In RV32, each instruction is of size 32 bits. In I-type instruction, I stand for immediate which means that operations use Registers and Immediate value for their execution and are not related with memory location. This instruction type is used in immediate and load operations. The entire 32 bits instruction is divided into 5 fields as shown below.

I-type

The first field in the instruction format is known as opcode, also referred as operation code. The opcode is of length 7 bits and is used to determine the type of instruction format.
The next subfield is known as rd field which is referred as Destination Register. The rd field is of length 5 bits and is used to store the final result of operation.
The next subfield is func3 also referred as function 3. Here the ‘3’ represents the size of this field. This field tells the detail about the operation, i.e., the type of arithmetic and logical that is performed.
The next subfield is the source registers, rs1 of length 5 bits. It is mainly used to store and manipulate the data during the execution of instructions.
The only difference between R-type and I-type is rs2 and func7 field of R-type has been replaced by 12-bits signed immediate, imm[11:0].

3. S-type Instruction
In RV32, each instruction is of size 32 bits. In S-type instruction, S stand for store which means it is store type instruction that helps to store the value of register into the memory. Mainly, this instruction type is used for store operations. The entire 32 bits instruction is divided into 6 fields as shown below.

s-type

The first field in the instruction format is known as opcode, also referred as operation code. The opcode is of length 7 bits and is used to determine the type of instruction format.
S-type instructions encode a 12-bit signed immediate, with the top seven bits imm[11:5] in bits [31:25] of the instruction and the lower five bits imm[4:0] in bits [11:7] of the instruction.
S-type instruction doesn’t have rd fields which states that these instructions are not used to write value to a register, but to write/store a value to a memory.
The value to be stored is defined in rs1 field and address to which we have to store this value is calculated using rs1 and immediate field. The width of the operation and types of instruction is defined by func3, it can be a word, half-word or byte.

4. B-type Instruction
In RV32, each instruction is of size 32 bits. In B-type instruction, B stand for branching which means it is mainly used for branching based on certain conditions. The entire 32 bits instruction is divided into 8 fields as shown below.

B-type

The first field in the instruction format is known as opcode, also referred as operation code. The opcode is of length 7 bits and is used to determine the type of instruction format.
B-type instructions encode a 12-bit signed immediate, with the most significant bit imm[12] in bit [31] of the instruction, six bits imm[10:5] in bits [25:30] of the instruction, four bits imm[4:1] in bits [11:8] and one bit imm[11] on bit[7].
There are two source registers rs1 and rs2 on which various operations are performed based on certain conditions, and those conditions are defined by func3 field.
After performing operations on the source register based on the conditions, it is evaluated that if the condition is true, Program Counter value gets updated by PC = Present PC Value + Immediate Value, and if the condition is false then PC will be given as PC = Present PC value + 4 bytes, which states that PC will move to next instruction set.
RV32 instructions are word-aligned, which means that address is always defined in the multiple of 4 bytes.

5. U-type Instruction
In RV32, each instruction is of size 32 bits. In U-type instruction, U stand for Upper Immediate instructions which means it is simply used to transfer the immediate data into the destination register. The entire 32 bits instruction is divided into 3 fields as shown below.

u-type

The first field in the instruction format is known as opcode, also referred as operation code. The opcode is of length 7 bits and is used to determine the type of instruction format.
The U-type instruction only consists of two instructions, i.e., LUI and AUIPC.
For Example, lets take the instruction lui rd, imm and understand this instruction. lui x15, 0x13579 : This instruction will be executed and the immediate value 0x13579 will be written in the MSB of the rd x15, and it will look like x15 = 0x13579000.

6. J-type Instruction
In RV32, each instruction is of size 32 bits. In U-type instruction, J stand for jump, which means that this instruction format is used to implement jump type instruction. The entire 32 bits instruction is divided into 6 fields as shown below.

j-type

The first field in the instruction format is known as opcode, also referred as operation code. The opcode is of length 7 bits and is used to determine the type of instruction format.
The J-type instruction only consists of single instruction, JAL.
J-type instruction encode 20 bits signed immediate which is divided into four fields.
The J-type instructions are often used to perform jump to the desired memory location. The address of the desired memory location is defined in the instruction. These instructions are also used to implement loops.

### Instruction 1: add x5, x6, x7  
- Format: R-Type  
- Opcode: 0110011  
- 32-bit Encoding: 0000000 00111 00110 000 00101 0110011  

### Instruction 2: sub x8, x9, x10  
- Format: R-Type  
- Opcode: 0110011  
- 32-bit Encoding: 0100000 01010 01001 000 01000 0110011  

### Instruction 3: and x11, x12, x13  
- Format: R-Type  
- Opcode: 0110011  
- 32-bit Encoding: 0000000 01101 01100 111 01011 0110011  

### Instruction 4: or x14, x15, x16  
- Format: R-Type  
- Opcode: 0110011  
- 32-bit Encoding: 0000000 10000 01111 110 01110 0110011  

### Instruction 5: xor x17, x18, x19  
- Format: R-Type  
- Opcode: 0110011  
- 32-bit Encoding: 0000000 10011 10010 100 10001 0110011  

### Instruction 6: sll x20, x21, x22  
- Format: R-Type  
- Opcode: 0110011  
- 32-bit Encoding: 0000000 10110 10101 001 10100 0110011  

### Instruction 7: srl x23, x24, x25  
- Format: R-Type  
- Opcode: 0110011  
- 32-bit Encoding: 0000000 11001 11000 101 10111 0110011  

### Instruction 8: lw x6, 12(x7)  
- Format: I-Type  
- Opcode: 0000011  
- 32-bit Encoding: 00001100 00111 010 00110 0000011  

### Instruction 9: sw x6, 12(x7)  
- Format: S-Type  
- Opcode: 0100011  
- 32-bit Encoding: 0000110 00110 00111 010 01100 0100011  

### Instruction 10: beq x5, x6, label  
- Format: B-Type  
- Opcode: 1100011  
- 32-bit Encoding: 000000 00110 00101 000 00000 1100011  

### Instruction 11: bne x7, x8, label  
- Format: B-Type  
- Opcode: 1100011  
- 32-bit Encoding: 000000 01000 00111 001 00000 1100011  

### Instruction 12: jal x1, label  
- Format: J-Type  
- Opcode: 1101111  
- 32-bit Encoding: 000000000000 00000 000 00001 1101111  

### Instruction 13: jalr x2, x3, 16  
- Format: I-Type  
- Opcode: 1100111  
- 32-bit Encoding: 00010000 00011 000 00010 1100111  

### Instruction 14: lui x4, 0x10000  
- Format: U-Type  
- Opcode: 0110111  
- 32-bit Encoding: 00010000000000000000 00100 0110111  

### Instruction 15: auipc x5, 0x20000  
- Format: U-Type  
- Opcode: 0010111  
- 32-bit Encoding: 00100000000000000000 00101 0010111

</details>

<details>
<summary><strong>Task 4:</strong> Task is to make use of RISCV Core: Verilog Netlist and Testbench, perform an experiment of Functional Simulation and observe the waveforms</summary>

we will use the Verilog Code and Testbench of RISCV that has already been designed. The reference GitHub repository is : iiitb_rv32i

### Steps to perform functional simulation of RISCV
1.Create a new directory with your name mkdir <your_name>

2.Create two files by using touch command as keerthi_rv32i.v and keerthi_rv32i_tb.v

3.Copy the code from the reference github repo and paste it in your verilog and testbench files

4.To run and simulate the verilog code, enter the following command:

```bash
$ iverilog -o iiitb_rv32i keerthi_rv32i.v keerthi_rv32i_tb.v
$ ./iiitb_rv32i
```

5.To see the simulation waveform in GTKWave, enter the following command:
```bash
$ gtkwave iiitb_rv32i.vcd
```

6.The GTKWave will be opened and following window will be appeared
![image](https://github.com/user-attachments/assets/d101e74c-e39c-4507-a0a9-f4d5346fb36c)

As shown in the figure below, all the instructions in the given verilog file is hard-coded. Hard-coded means that instead of following the RISCV specifications bit pattern, the designer has hard-coded each instructions based on their own pattern. Hence the 32-bits instruction that we generated in Task-2 will not match with the given instruction.

![image](https://github.com/user-attachments/assets/713b456e-d112-45e8-80ef-1325194bc23a)

### Difference Between Standard RISC-V ISA and Hardcoded ISA

| **Operation**           | **Standard RISC-V ISA** | **Hardcoded ISA (Reference Repo)** |
|-------------------------|-------------------------|-------------------------------------|
| `ADD R6, R2, R1`        | `32'h00110333`          | `32'h02208300`                      |
| `SUB R7, R1, R2`        | `32'h402083b3`          | `32'h02209380`                      |
| `AND R8, R1, R3`        | `32'h0030f433`          | `32'h0230a400`                      |
| `OR R9, R2, R5`         | `32'h005164b3`          | `32'h02513480`                      |
| `XOR R10, R1, R4`       | `32'h0040c533`          | `32'h0240c500`                      |
| `SLT R1, R2, R4`        | `32'h0045a0b3`          | `32'h02415580`                      |
| `ADDI R12, R4, 5`       | `32'h004120b3`          | `32'h00520600`                      |
| `BEQ R0, R0, 15`        | `32'h00000f63`          | `32'h00f00002`                      |
| `SW R3, R1, 2`          | `32'h0030a123`          | `32'h00209181`                      |
| `LW R13, R1, 2`         | `32'h0020a683`          | `32'h00208681`                      |
| `SRL R16, R14, R2`      | `32'h0030a123`*         | `32'h00271803`                      |
| `SLL R15, R1, R2`       | `32'h002097b3`          | `32'h00208783`                      |

Analysing the Output Waveform of various instructions that we have covered in TASK-2

Instruction 1: ADD 
![image](https://github.com/user-attachments/assets/02ad32af-307a-449d-a304-0f738a652c86)

Instruction 2: SUB
![image](https://github.com/user-attachments/assets/4e7e4c31-78b2-4daf-82dc-f7f650ac18aa)

Instruction 3: AND 
![image](https://github.com/user-attachments/assets/4e44c9fa-e158-428a-89f4-c0052a217e79)

Instruction 4: OR 
![image](https://github.com/user-attachments/assets/8b064f4d-be8a-4cf5-a6f2-f5d45b80e3d8)

Instruction 5: XOR 
![image](https://github.com/user-attachments/assets/5ecd0f7c-e43f-446c-b2f3-d5448cf07c1b)

Instruction 6: SLT
![image](https://github.com/user-attachments/assets/d8293ca4-5533-4396-86cc-cd2f3be1411c)

Instruction 7: ADDI 
![image](https://github.com/user-attachments/assets/5d2bafa3-89a6-4233-b1a9-b8bd7d251256)

Instruction 8: BEQ 
![image](https://github.com/user-attachments/assets/0d82b2b5-5b91-4575-a6f8-c04e1dcffd15)


</details>

<details>
<summary><strong>Task 5:</strong> Task is to provide details of the project </summary>

### LDR-based Automatic Night Light 

### Overview
The LDR-based Automatic Night Light project demonstrates an intelligent lighting system that utilizes a Light Dependent Resistor (LDR) in combination with the CH32V003 RISC-V processor on the VSDMini Quadron board. This project automatically turns on an LED in low-light conditions and switches it off when sufficient ambient light is detected. The LDR continuously senses the light intensity, and based on the analog value converted to digital using a comparator or GPIO input logic, the CH32V003 controls the LED accordingly. This smart lighting system is highly energy-efficient and eliminates the need for manual operation, making it ideal for night lamps, street lights, and hallway lights.

### Components Required
1.VSDMini Quadron (CH32V003x) board
2.LDR (Light Dependent Resistor)
3.10kΩ Resistor
4.LED
5.Jumper wires
6.Breadboard
7.Power Supply (5V USB-C or regulated 3.3V)

### Working Principle
An LDR (Light Dependent Resistor) changes its resistance based on the ambient light:
1.In bright light, its resistance is low.
2.In darkness, its resistance is high.

This property is used in a voltage divider circuit with a fixed resistor (typically 10kΩ). The voltage across the fixed resistor increases when the LDR is in the dark, and this voltage is sensed using a GPIO pin configured as a digital input on the CH32V003. Based on the input:
1.If it’s dark, the microcontroller turns ON the LED.
2.If it’s bright, the microcontroller turns OFF the LED.

### Circuit Connection for Night Light
Voltage Divider Setup:
One end of LDR → VCC (3.3V)
Other end of LDR → GPIO Input Pin (D3) and one end of 10kΩ Resistor
Other end of 10kΩ Resistor → GND

LED Setup:
Anode (+) of LED → GPIO Output Pin (D6) (through 330Ω resistor)
Cathode (–) of LED → GND

This setup lets the GPIO input pin (D3) read a high or low signal depending on light intensity, while D6 controls the LED output.

### Pin Connection Table

| Component   | Pin on VSDMini (CH32V003x) |
|-------------|-----------------------------|
| LDR Output  | D3                          |
| LED Anode   | D6                          |
| GND         | GND                         |
| VCC (3.3V)  | VIN                         |

### How to do

```bash

#include <ch32v003fun.h>

#define LDR_PIN     GPIO_Pin_1  // D3 -> PA1 (ADC_IN1)
#define LED_PIN     GPIO_Pin_2  // D6 -> PA2

void setup_adc()
{
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_ADC1 | RCC_APB2Periph_GPIOA, ENABLE);

    GPIO_InitTypeDef gpio;
    gpio.GPIO_Pin = LDR_PIN;
    gpio.GPIO_Mode = GPIO_Mode_AIN;
    GPIO_Init(GPIOA, &gpio);

    ADC1->CTLR2 |= ADC_EXTTRIGConv_None;
    ADC1->CTLR2 |= ADC_ADON;
    Delay_Ms(1);
    ADC1->CTLR2 |= ADC_ADON;
}

uint16_t read_adc()
{
    ADC1->SAMPTR2 = ADC_SampleTime_239Cycles5 << ADC_Channel_1_Pos;
    ADC1->RSQR3 = 1;
    ADC1->CTLR2 |= ADC_SWSTART;
    while (!(ADC1->STATR & ADC_STATR_EOC));
    return ADC1->RDATAR;
}

int main()
{
    SystemInit();
    Delay_Init();

    // Setup LED pin
    GPIO_InitTypeDef gpio_led;
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOA, ENABLE);
    gpio_led.GPIO_Pin = LED_PIN;
    gpio_led.GPIO_Speed = GPIO_Speed_10MHz;
    gpio_led.GPIO_Mode = GPIO_Mode_Out_PP;
    GPIO_Init(GPIOA, &gpio_led);

    // Setup ADC for LDR
    setup_adc();

    while (1)
    {
        uint16_t ldr_value = read_adc();

        if (ldr_value < 1000)  // Adjust threshold as needed
        {
            GPIO_ResetBits(GPIOA, LED_PIN); // LED ON
        }
        else
        {
            GPIO_SetBits(GPIOA, LED_PIN);   // LED OFF
        }

        Delay_Ms(200);
    }
}
```
### Code explation
Code Breakdown:
1.Header Files:
#include <ch32v003fun.h>: This header file includes the necessary functions for the CH32V003 microcontroller, including GPIO, ADC, and delay functions.

2.Pin Definitions:
LDR_PIN: Defined as GPIO_Pin_1 (connected to PA1, ADC channel 1), where the LDR sensor is connected to measure light intensity.
LED_PIN: Defined as GPIO_Pin_2 (connected to PA2), which controls the LED for the night light.

3.setup_adc() Function:
Configures the ADC (Analog-to-Digital Converter) to read from PA1 (LDR pin). The ADC is set up to use the internal reference voltage and the LDR's analog signal will be converted to a digital value.

4.The RCC_APB2PeriphClockCmd function enables the clock for ADC1 and GPIOA, allowing their use.

5.The GPIO_InitTypeDef structure is used to configure the LDR pin (PA1) as an analog input.

6.read_adc() Function:
Sets the sampling time for ADC readings and starts the conversion by setting ADC_SWSTART.
The function waits until the ADC conversion is complete (when the EOC flag is set).
The ADC result is read from ADC1->RDATAR and returned as a 16-bit value.

7.Main Function:
The main function initializes the system and the delay function.
The LED pin (PA2) is initialized as an output pin, set to push-pull mode.
The ADC is set up for reading the LDR.
The program enters a while(1) loop where it continuously:
Reads the ADC value of the LDR.
If the LDR value is below a defined threshold (1000 in this case), the LED is turned ON (GPIO_ResetBits(GPIOA, LED_PIN)).
If the LDR value is above the threshold, the LED is turned OFF (GPIO_SetBits(GPIOA, LED_PIN)).
A 200 ms delay is added for smooth operation.
