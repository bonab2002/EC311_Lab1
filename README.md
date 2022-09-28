# Lab 1: Design 4-bit binary Adder-Subtractor and ALU
 Due Date: Due by October 14, 2022

**Please submit the lab in the format mentioned below.**

## Submission instructions
There are two main parts in lab-1: 1) Designing a 4-bit adder/subtractor; 2) Designing a 4-bit ALU.

### Folders Structure
There are following 2 folders in the main folder ("EC311_Lab1_Template"):
  - (1) "add_sub_4_bit"
  - (2) "alu_4_bit"
  
You will place the solution code for part-1 of lab-1, i.e., the 4-bit binary adder-subtractor in the folder named "add_sub_4_bit", and the solution code for part-2 of lab-1, i.e., the 4-bit Arithmetic-Logic Unit (ALU) in the folder named "alu_4_bit".

### Lab-1 Part-1 Folder Structure & Signal Naming
The main solution code for the part-1 of lab-1 should be inside the file in the following path:
- *EC311_Lab1_Template/add_sub_4_bit/add_sub_4_bit.v*

Do not changed the names of the output ports or the module name for your top file.


### Lab-1 Part-2 Folder Structure & Signal Naming
The main solution verilog code for the part-2 of lab-1 should be inside the file in the following path:
- *EC311_Lab1_Template/alu_4_bit/alu_4_bit.v*

Do not changed the names of the output ports or the module name for your top file.

## Change the YML file inside EC311_Lab1_Template/.github/workflows/classroom.yml

Do the following steps so that your code can be graded automatically:
 - Open the file EC311_Lab1_Template/.github/workflows/verify.yml
 - Copy the code from line-9 till the end, the following lines: 
```
    steps:
    - uses: actions/checkout@v2

    - uses: actions/cache@v3
      with:
        path: ~/.cache/pip
        key: ${{ runner.os }}-pip-${{ hashFiles('**/requirements.txt') }}
        restore-keys: |
          ${{ runner.os }}-pip-
    
    - name: Set up Python 3.9
      uses: actions/setup-python@v2
      with:
        python-version: 3.9

    - name: Install dependencies
      run: |
        pip3 install -r requirements.txt
        sudo apt install -y --no-install-recommends iverilog
    - name: Verify with cocotb & icarus
      run: |
        pytest register/tb axis_fifo/tb
```
 
