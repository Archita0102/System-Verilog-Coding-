# System-Verilog-Coding

A detailed summary of System Verilog Assignments from an Udemy course

## Table of Contents 
  
 * [Assignment 1: Signals](#assignment-1)
 * [Assignment 2: Signals](#assignment-2)
 * [Assignment 3: Signals](#assignment-3)
* [Assignment 4: Signals](#assignment-4)
* [Assignment 5: Variables](#assignment-5)
* [Assignment 6: Initialization of arrays](#assignment-6)
* [Assignment 7: Signals](#assignment-6) 
     
 * [Acknowledgement](#acknowledgement) 
 
  
  
 #### Assignment 1: 
 ##### Assume System Consist of two global signals resetn and clk. Use an initial block to initialize clk to 1'b0 and resetn to 1'b0. User must keep resetn in an active low state for 60 nSec at the start of the simulation and then make active high. Assume `timescale 1ns/1ps

  ####  Assignment 2: 
  ##### Assume `timescale 1ps/1ps. Generate a 25 MHz square wave waveform for the Signal clk


  ####  Assignment 3: 
  #####  Write a code to generate a 9MHz square waveform for the signal sclk. Assume timescale with 1nsec time-unit and 3 digit precision.


  ####  Assignment 4: 
 ##### Write a function capable of generating a square waveform with the help of period(in nSec) and duty cycle(0 to 1). The phase difference is assumed to be 0 for the entire system operation. Verify function behavior by generating waveform for the signal clk with period: 40 nsec and duty cycle: 0.4


  ####  Assignment 5: 
 ##### Assume you have four variables ( a, b,c, and d )  in your testbench top. a and b are of the 8-bit reg type, while c and d are of the integer type. initialize a,b,c, and d to values of 12, 34, 67, and 255 respectively. Add a code to print the values of all the variables after 12 nSec.
 
 `timescale 1ns/1ps

module tb();
   
  byte a=0;
  byte b=0;
  int c=0;
  int d=0;
  
  initial begin
    a=8'd12;
    b=8'd64;
    c=67;
    d=255;
  end
  
  initial begin
    $display("Values of a : %0d  b:%0d  c:%0d and d:%0d",a,b,c,d);
  end
endmodule


  ####  Assignment 6: 
 ##### Create an array capable of storing 10 elements of an unsigned integer. Initialize all the 10 elements to a value equal to the square of the index of that element. for e.g. first element has index no. 0 so initialize it to 0, the second element has index no. 1 so initialize it to 1, the third element has index no. 2 so initialize it to 4, and so on. Verify the code by sending values of all the elements on Console.c.

 `timescale 1ns/1ps

module tb();
	
  int arr[10];
  int i=0;
  
  initial begin
    for(i=0;i<$size(arr);i++)
    begin
      arr[i]=i**2;
    end
  end
  initial begin
  $display("Value of the array : %0p",arr);
  end
endmodule


####  Assignment 7: 
 ##### Assume you have four variables ( a, b,c, and d )  in your testbench top. a and b are of the 8-bit reg type, while c and d are of the integer type. initialize a,b,c, and d to values of 12, 34, 67, and 255 respectively. Add a code to print the values of all the variables after 12 nSec.

 
