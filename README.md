# ALU | Model ARM Microprocessor

## Background
This is an Arithmetic Logic Unit microprocessor based on ARM architecture made in Logisim. This logic unit can be used to create loops and conditional statements to make calculations and logical decisions. It operates on binary numbers, manipulating individual bits based on the desired operation. The ALU takes input from registers, processes the data according to the specified operation, and produces an output that can be stored back in registers. The registers and RAM are in HEX for visualization. 

![Max100 Demo](https://github.com/SarthakSarans/ALU/assets/63066248/1312c74a-0039-4836-9fc3-a913eac36115)
Demonstration of finding the maximum value from a set of 100 random signed 16-bit numbers. Final answer: 3fff

## Components

- Python Assembler
- 16-Bit Carry Select Adder
- Overflow Detection
- IR Decoder
- Program Counter
- Cycle Counter
- Data RAM
- Cache
- Registers
- Flip Flops
- Multiplexers
- Write Enable

## Assembler Usage
Once the program is run, type in the name of the .txt file you would like to run and the assembler will generate a set of instructions that can be pasted in the Cache to run properly.

To use the assembler script, you must follow the highlighted instruction codes below. To see example function, see the Test Files folder above.


## Instructions

| Instruction       | [7:6] | [5:4]     | [3:0]      | Format      | Description |
| :---        |    :----:   |    :----:     |    :----:   |    :----:   | :---        |
|Addition ```add```      | Rd       | Rs   |0010        | add Rd, Rs        | Rd = Rd + Rs     |
|Subtract ```sub```      | Rd       | Rs   |0011        | sub Rd, Rs        | Rd = Rd - Rs     |
|Load Immediate ```ldi```      | Rd       | val   |1110        | ldi Rd, val        | Rd = val     |
|Load ```ld```      | Rd       | Rs   |1111        | ld Rd, Rs        | Rd = data[Rs<sub>3:0</sub>]    |
|Move ```mov```      | Rd       | Rs   |0110        | mv Rd, Rs        | Rd = Rs     |
|Store ```st```      | Rd       | Rs   |1011        | st Rd, Rs        | data[Rs<sub>3:0</sub>] = Rd      |
|No Operation ```nop```      | 00       | 00   |0110        | nop        | changes nothing     |

| Instruction       | [7:2]  | [1:0]      | Format      | Description |
| :---        |    :----:   |    :----:     |    :----:   | :---        |
| Jump ```jmp```      | target PC   | 00        | jmp label        | PC = targ PC     |
|Conditional Jump ```jmpn```      | target pC       | 01   |jmpn label        | if r<0 PC = targ PC        |

### Addition
Takes the sum of the two input registers and stores in Rd register.

### Subtraction
Takes the difference of the two input registers and stores in Rd register.

### Load Immediate
Takes an input from 0-3 and stores it in the Rd register.

### Load
Takes an input to a location in the data RAM and stores it in the Rd register.

### Move
Stores the value of Rs in Rd. After moving, value in Rs doesn't change.

### Store
Takes an input location (Rs) and stores Rd at that location in the data RAM.

### No Operation
Moves from R3 to R3 and thus doesn't change any values. This is used to buffer pipeline stages to ensure operations compute properly.

### Jump
Jumps from one section of code to another, specified by the label given.

### Conditional Jump
r is the top bit of the previous result from the adder

Checks if r is negative and if true then jumps to the section specified by the label given. This is essentially an 'if' statement that has to be satisfied to perform a jump.



