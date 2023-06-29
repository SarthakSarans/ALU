# ALU | Model ARM Microprocessor
Arithmetic Logic Unit microprocessor based on ARM architecture made in Logisim

![Max100 Demo](https://github.com/SarthakSarans/ALU/assets/63066248/1312c74a-0039-4836-9fc3-a913eac36115)
Demonstration of finding the maximum value from a set of 100 random signed 16-bit numbers being 3fff

## Instructions

| Instruction       | [7:6] | [5:4]     | [3:0]      | Format      | Description |
| :---        |    :----:   |    :----:     |    :----:   |    :----:   | :---        |
|Addition ```add```      | Rd       | Rs   |0010        | add Rd, Rs        | Rd = Rd + Rs     |
|Subtract ```sub```      | Rd       | Rs   |0011        | sub Rd, Rs        | Rd = Rd - Rs     |
|Load Immediate ```ldi```      | Rd       | val   |1110        | ldi Rd, val        | Rd = val     |
|lLoad ```ld```      | Rd       | Rs   |1111        | ld Rd, Rs        | Rd = data[Rs<sub>3:0</sub>]    |
|Move ```mov```      | Rd       | Rs   |0110        | mv Rd, Rs        | Rd = Rs     |
|Store ```st```      | Rd       | Rs   |1011        | st Rd, Rs        | data[Rs<sub>3:0</sub>] = Rd      |
|No Operation ```nop```      | 00       | 00   |0110        | nop        | changes nothing     |

| Instruction       | [7:2]  | [1:0]      | Format      | Description |
| :---        |    :----:   |    :----:     |    :----:   | :---        |
| Jump ```jmp```      | target PC   | 00        | jmp label        | PC = targ PC     |
|Conditional Jump ```jmpn```      | target pC       | 01   |jpmn label        | if <mark>r</mark><0 PC = targ PC        |

r is the top bit of the previous adder result

