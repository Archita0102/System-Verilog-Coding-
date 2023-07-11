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
 ##### Create two arrays of reg type capable of storing 15 elements. Use $urandom function to add 15 values to the array. Print the value of all the elements of the array on a single line.

`timescale 1ns/1ps

module tb();
	
  int arr[15];
  int arr2[15];
  int i=0;
  
  initial begin
    for(i=0;i<$size(arr);i++)
    begin
      arr[i]=$urandom();
    end
    for(i=0;i<$size(arr2);i++)
    begin
      arr2[i]=$urandom();
    end
  end
  initial begin
  $display("Value of the array : %0p",arr);
    $display("Value of the array : %0p",arr2);
  end
endmodule

####  Assignment 8: 
 ##### Create a dynamic array capable of storing 7 elements. add a value of multiple of 7 starting from 7 in the array (7, 14, 21 ....49). After 20 nsec Update the size of the dynamic array to 20. Keep existing values of the array as it is and update the rest 13 elements to a multiple of 5 starting from 5. Print Value of the dynamic array after updating all the elements.

Expected result : 7, 14, 21, 28 ..... 49, 5, 10, 15 ..... 65 .

`timescale 1ns/1ps

module tb();
	
  int arr[];
  
  int i=0;
  int j=0;
  initial begin
    arr=new[7];
    for(i=0;i<7;i++)
        begin
          arr[i]=(i+1)*7;
        end
    $display("%0p",arr);
     #20;
    j=20;
    arr=new[j](arr);
    for(i=7;i<j;i++)
        begin
          arr[i]=(i-6)*5;
        end    
    $display("%0p",arr);
    
   
  end
  
endmodule


####  Assignment 9: 
 ##### Create a Fixed-size array capable of storing 20 elements. Add random values to all the 20 elements by using $urandom function. Now add all the elements of the fixed-size array to the Queue in such a way that the first element of the Fixed-size array should be the last element of the Queue. Print all the elements of both fixed-size array and Queue on Console.

`timescale 1ns/1ps

module tb();
	
  int arr1[20];
  int arr2[$];
  
  initial begin
    for (int i=0;i<$size(arr1);i++)
      begin
        arr1[i]=$urandom_range(1,5);
      end
    $display("%0p",arr1); 
    for(int i=0;i<$size(arr1);i++)
      begin
        arr2[i]=arr1[19-i];
      end
    $display("%0p",arr2);
  end
  
 
endmodule
