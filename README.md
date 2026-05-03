# FPGA_Internship_screening
# Module 1 - Introduction to to Verilog RTL Design And synthesis
## introduction to open-source simulator iverilog
## Labs using Iverilog abd gtkwave
codes used
```bash
iverilog -o good_mux.vvp good_mux.v tb_good_mux.v
./a.out
gtkwave tb_good_mux.vcd
```
![introduction to open-source simulator iverilog](images/images/Screenshot1.png)
![introduction to open-source simulator iverilog](images/images/Screenshot2.png)
![introduction to open-source simulator iverilog](images/images/Screenshot3.png)

---
## Introduction to Yosys and logic Synthesis
## Labs using Yosys and sky130PDKs
Codes used
``` bash
yosys> read_liberty -lib lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> read_verilog dff_asyncres.v
yosys> synth -top dff_asyncres
yosys> abc -liberty lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> show
```
![introduction to open-source simulator iverilog](images/images/Screenshot4.png)
![introduction to open-source simulator iverilog](images/images/Screenshot5.png)
![introduction to open-source simulator iverilog](images/images/Screenshot6.png)
![introduction to open-source simulator iverilog](images/images/Screenshot7.png)


---
## Module 2- Timing libs, hierichal vs flat synthesis and efficient flop coding styles
### Introduction to timing.lib
```bash
# Open the library file using the leaf text editor
gvim lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```
![introduction to open-source simulator iverilog](images/images/Screenshot8.png)

```bash
# Check the files in the directory
ls

# View the design to see the hierarchy
gvim multiple_modules.v
# Start Yosys
yosys

# Read library and design files
yosys> read_liberty -lib lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> read_verilog multiple_modules.v

# Synthesize the top-level module
yosys> synth -top multiple_modules

# Map to the library
yosys> abc -liberty lib/sky130_fd_sc_hd__tt_025C_1v80.lib

# View the hierarchy
yosys> show multiple_modules
yosys> write_verilog -noattr trans_hier.v
```
![introduction to open-source simulator iverilog](images/images/Screenshot9.png)
<img width="1920" height="1080" alt="Screenshot (3)" src="https://github.com/user-attachments/assets/c93252c8-1d22-4f1e-9c00-1e3139f4ab9f" />
<img width="1920" height="1080" alt="Screenshot (4)" src="https://github.com/user-attachments/assets/be15ba5d-a920-4ce9-811f-dfa7672c5d6d" />
<img width="1920" height="1080" alt="Screenshot (5)" src="https://github.com/user-attachments/assets/011479f4-b8ee-4304-819d-b92cbacb1b67" />
<img width="1920" height="1080" alt="Screenshot (6)" src="https://github.com/user-attachments/assets/bc96ddf0-d6c4-49cc-a601-b82dc0a291ac" />
<img width="1920" height="1080" alt="Screenshot (7)" src="https://github.com/user-attachments/assets/a67cd5fb-cd58-46a3-98fa-d815a1c87b34" />
<img width="1920" height="1080" alt="Screenshot (8)" src="https://github.com/user-attachments/assets/a49446dd-99a5-42bb-b77e-86559d4f8d5c" />
<img width="1920" height="1080" alt="Screenshot (9)" src="https://github.com/user-attachments/assets/575edf22-6904-48a2-83e5-de74d7f67d89" />
<img width="1920" height="1080" alt="Screenshot (11)" src="https://github.com/user-attachments/assets/72cf42b9-2ecb-44c8-b2e2-af71d0189e46" />
<img width="1920" height="1080" alt="Screenshot (13)" src="https://github.com/user-attachments/assets/290c6a9c-1a90-4d9c-a436-99e0bd5ad4a4" />




```bash
read_liberty -lib lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog multiple_modules.v

synth -top multiple_modules

flatten

abc -liberty lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show
```

<img width="1920" height="1080" alt="Screenshot (16)" src="https://github.com/user-attachments/assets/b9fdc7ae-2744-44c5-bcd1-2fd0a76b6bdd" />
<img width="1920" height="1080" alt="Screenshot (20)" src="https://github.com/user-attachments/assets/fd6acae2-cafc-4c3c-91d0-555df9cf5034" />
<img width="1920" height="1080" alt="Screenshot (21)" src="https://github.com/user-attachments/assets/c9a5253e-db3f-4ac8-ba2a-7c0bec238146" />
<img width="1920" height="1080" alt="Screenshot (22)" src="https://github.com/user-attachments/assets/6fac9789-5fe5-4e9e-93ed-972a0a693514" />
<img width="1920" height="1080" alt="Screenshot (24)" src="https://github.com/user-attachments/assets/72d1a6f3-3e49-48e9-90d3-ff2bb6afd7ee" />
<img width="1920" height="1080" alt="Screenshot (25)" src="https://github.com/user-attachments/assets/f793a6f7-162f-4008-8b75-63080e7f124e" />
<img width="1920" height="1080" alt="Screenshot (26)" src="https://github.com/user-attachments/assets/b207c57b-7e21-45a7-ac17-535c04d750d9" />
<img width="1920" height="1080" alt="Screenshot (27)" src="https://github.com/user-attachments/assets/ce05f2db-25b6-4762-b8d3-8aa459d116ab" />
<img width="1920" height="1080" alt="Screenshot (31)" src="https://github.com/user-attachments/assets/72daf7f1-50a2-432b-ba60-da58a4b272e6" />
<img width="1920" height="1080" alt="Screenshot (32)" src="https://github.com/user-attachments/assets/8499c000-8e39-40af-a9b0-e4f6ab13f7a3" />
<img width="1920" height="1080" alt="Screenshot (34)" src="https://github.com/user-attachments/assets/c11e4777-6e2e-4d39-af5b-95869e8ede5d" />
<img width="1920" height="1080" alt="Screenshot (35)" src="https://github.com/user-attachments/assets/d387aab1-d1ab-44ec-9953-cdfc23d1bcb5" />
<img width="1920" height="1080" alt="Screenshot (39)" src="https://github.com/user-attachments/assets/62b1e765-f101-40cd-8e44-ddebf135f365" />
<img width="1920" height="1080" alt="Screenshot (43)" src="https://github.com/user-attachments/assets/da754caf-d560-4fd2-afcf-1ea5ec0a6d7a" />










