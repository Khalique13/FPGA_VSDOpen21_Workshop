
# Digital Design on FPGA VSDOpen21 Workshop

![vsdopentutorial](https://user-images.githubusercontent.com/80625515/137896513-0cc9dace-0454-43a7-be28-a6ce883cf631.png)


## Table of Contents

- [Introduction](#introduction)
- [Benefits](#benefits-of-virtual-fpga)
- [Verilog](#verilog)
- [Makerchip](#makerchip)
- [Interfacing LEDs](#interfacing-leds)
- [Seven Segment Display](#seven-segment-display)
- [4-way Traffic Light Controller](#4-way-traffic-light-controller)
- [Finite State Machines](#finite-state-machines)
- [Traffic Light Controller Lab](#traffic-light-controller-lab)
- [References](#references)
- [Author](#author)
- [Acknowledgement](#acknowledgement)

## Introduction

FPGA also known as Field-Programmable Gate Array, is a hardware circuit board that executes hardware models. It is used for prototyping ASICs and Processors.
This workshop is to learn and understand Digital Design using Virtual FPGA.

![Virtual_FPGA](https://user-images.githubusercontent.com/80625515/138098267-8756ed97-1171-4c35-a865-1465c3b42c65.png)



## Benefits of Virtual FPGA

1. Virtual demo FPGA visualizations
2. Access to various kinds of Board
3. Debug each & every cycle
4. Open-source (Freely access to all)

The detailed information on Virtual FPGA Lab can be found [here](https://github.com/BalaDhinesh/Virtual-FPGA-Lab.git)


## Verilog

- Hardware Description Language
- Verification 
  - Simulation
  - Timing Analysis
  - Test Analsis
  - Synthesis
- Level of Abstraction 
  - Behavioural Level
  - Register-Transfer Level
  - Gate Level

## Makerchip 

Makerchip is a free IDE which is used to develop Integrated Circuits, where you can design, compile, and simulate hardware using verilog all from your browser. It is available as https://makerchip.com/.

![Screenshot from 2021-10-20 18-18-20](https://user-images.githubusercontent.com/80625515/138098474-9fa1cfa1-81f9-4a58-9d7d-068483d4a7af.png)



## Interfacing LEDs

![Snap-1](https://user-images.githubusercontent.com/80625515/138098510-93a7bf46-c3a2-41f5-9e79-42e9c9e0385f.png)


### Assigning random values to the LEDs

![snap-2](https://user-images.githubusercontent.com/80625515/138098542-84bc8015-7d37-427c-9740-31a7d50a5fed.png)


### LED Binary Counter

![counter-gif](https://user-images.githubusercontent.com/80625515/138130852-a8a97faa-12cb-4bc9-afcd-c8c97949069d.gif)


### Interfacing LED Lab 

![lab1](https://user-images.githubusercontent.com/80625515/138124739-d1545d84-fdad-4363-a568-24a45eb46237.gif)


## Seven Segment Display

![seven-seg-display-prob](https://user-images.githubusercontent.com/80625515/138107446-6b86aa73-6740-4577-9bc7-c9ca9f032cba.png)

### Design of Seven-Segment Display

![design-7-display](https://user-images.githubusercontent.com/80625515/138107786-7a4622a1-24e0-4ff0-809b-51bac3187802.png)

### Interfacing Seven Segment Display

![Screenshot from 2021-10-20 13-00-03](https://user-images.githubusercontent.com/80625515/138108059-6f6d522c-f322-4c05-a941-2b20c0f0b458.png)

### Interfacing Seven Segment Display lab

![lab-2](https://user-images.githubusercontent.com/80625515/138129945-4121ee36-c364-451f-94f0-731f4e0236ac.gif)

## 4-way Traffic Light Controller
### Problem Statement

![prob-statement](https://user-images.githubusercontent.com/80625515/138134803-6f3b3b1f-fa2d-43b2-ab63-db88e11f9bfb.png)

## Finite State Machines

- Abstract model of computation that is used to model logic
- Based on the current state and a given input the machine performs state transitions and produces outputs.
- Two basic types are Mealy and Moore mahines

![fsm-model](https://user-images.githubusercontent.com/80625515/138136268-3a721727-e955-4e50-82bc-a620e161f94d.png)


### Verilog Code for NORTH, SOUTH, EAST and WEST
```
NORTH :
                    begin                      
                       // Enable first seven segment and set to Green 
                       digit <= 4'b0111;
                       segment <= 7'b1110111;
                        /* TODO: 1. Keep the green NORTH signal active for 8 seconds 
                                2. Set state of signal to yellow NORTH after that 
                          HINT: Use if-else block
                        */
                       if(count==7) begin
                             assign state=NORTH_Y;
                        	  assign count=0;    
                          end
                       else assign count=count+1;   
                    end
  ```

### Verilog Code for NORTH_Y, SOUTH_Y, EAST_Y and WEST_Y
```
NORTH_Y :
                    begin
                        // Enable first seven segment and set to Yellow
                        digit <= 4'b0111;
                        segment <= 7'b1111110;
                        /* TODO: 1. Keep the yellow NORTH signal active for 4 seconds 
                                2. Set state of signal to green SOUTH after that 
                        */
                      if(count==3) begin
                             assign state=SOUTH;
                        	  assign count=0;    
                          end
                       else assign count=count+1;
							end
  ```
## Traffic Light Controller Lab

![final-lab](https://user-images.githubusercontent.com/80625515/138137443-f6c83757-325d-48d3-8e81-53dfe5311f10.gif)



## References
- https://github.com/BalaDhinesh/Digital-Design-on-FPGA--VSDOpen21.git
- https://github.com/Eyantra698Sumanto/Digital-Design-on-FPGA.git

## Author
- Mohammad Khalique khan, Bachelor of Technology (ECE), Aliah University.

## Acknowledgement
- Bala Dhinesh, Undergrad, IIT Madras
- Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.
- Anagha Ghosh, VSD Corp. Pvt. Ltd.


