# Exercise-07-Multiplexer-and-De-multiplexer
### AIM: To implement 4 X1 multiplexer and 1X4 de multiplexer using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## What are Multiplexer and Demultiplexer?
In-network transmission, both the multiplexer and demultiplexer are combinational circuits. A multiplexer selects an input from several inputs then it is transmitted in the form of a single line. An alternative name of the multiplexer is MUX or data selector. A demultiplexer uses one input signal and generates many. So it is known as Demux or data distributor.

## What is a Multiplexer?
The multiplexer is a device that has multiple inputs and single line output. The select lines determine which input is connected to the output, and also increase the amount of data that can be sent over a network within a certain time. It is also called a data selector.

The single-pole multi-position switch is a simple example of a non-electronic circuit of the multiplexer, and it is widely used in many electronic circuits. The multiplexer is used to perform high-speed switching and is constructed by electronic components.

![image](https://user-images.githubusercontent.com/36288975/170912485-73c395c7-23c0-4e78-a53d-a2f0d07d9662.png)
          Figure-01 multiplexer block diagram 

Multiplexers are capable of handling both analog and digital applications. In analog applications, multiplexers are made up of relays and transistor switches, whereas in digital applications, the multiplexers are built from standard logic gates. When the multiplexer is used for digital applications, it is called a digital multiplexer.

4-to-1 Multiplexer
The 4X1 multiplexer comprises 4-input bits, 1- output bit, and 2- control bits. The four input bits are namely 0, D1, D2, and D3, respectively; only one of the input bits is transmitted to the output. The o/p ‘q’ depends on the value of control input AB. The control bit AB decides which of the i/p data bit should transmit the output. The following figure shows the 4X1 multiplexer circuit diagram using AND gates. For example, when the control bits AB =00, then the higher AND gates are allowed while remaining AND gates are restricted. Thus, data input D0 is transmitted to the output ‘q”
![image](https://user-images.githubusercontent.com/36288975/170912568-3598c60a-5035-41f3-b0c4-ccedba13aca5.png)


Figure2 4X1 multiplexer 
If the control input is changed to 11, then all gates are restricted except the bottom AND gate. In this case, D3 is transmitted to the output, and q=D0. If the control input is changed to AB =11, all gates are disabled except the bottom AND gate. In this case, D3 is transmitted to the output, and q = D3. The best example of a 4X1 multiplexer is IC 74153. In this IC, the o/p is the same as the i/p. Another example of a 4X1 multiplexer is IC 45352. In this IC, the o/p is the compliment of the i/p


## What is Demultiplexer?
De-multiplexer is also a device with one input and multiple output lines. It is used to send a signal to one of the many devices. The main difference between a multiplexer and a de-multiplexer is that a multiplexer takes two or more signals and encodes them on a wire, whereas a de-multiplexer does reverse to what the multiplexer does.
![image](https://user-images.githubusercontent.com/36288975/170912606-a30e4b74-1726-4430-b245-2c3c3d9c232d.png)
Figure 3 De-multiplexer 
1-4 Demultiplexer
The 1-to-4 demultiplexer comprises 1- input bit, 4-output bits, and control bits. The 1X4 demultiplexer circuit diagram is shown below.![image](https://user-images.githubusercontent.com/36288975/170912683-00fb746a-1d45-4023-91d1-3a70b841073c.png)

![image](https://user-images.githubusercontent.com/36288975/170912741-7cbd52af-7e0d-4be3-b5c6-6fb9c4eca7c9.png)

Figure4 1X4 De-multiplexer 
The i/p bit is considered as Data D. This data bit is transmitted to the data bit of the o/p lines, which depends on the AB value and the control i/p.

When the control i/p AB = 01, the upper second AND gate is permitted while the remaining AND gates are restricted. Thus, only data bit D is transmitted to the output, and Y1 = Data.

If the data bit D is low, the output Y1 is low. IF data bit D is high, the output Y1 is high. The value of the output Y1 depends upon the value of data bit D, the remaining outputs are in a low state.

If the control input changes to AB = 10, then all the gates are restricted except the third AND gate from the top. Then, data bit D is transmitted only to the output Y2; and, Y2 = Data. . The best example of 1X4 demultiplexer is IC 74155.

 
 
### Procedure
/* write all the steps invloved */



### PROGRAM 
/*
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: 212221230094
RegisterNumber:A.Sharmila
*/
```
## Multiplexer
module ex07(I0,I1,I2,I3,S0,S1,Y);
input I0,I1,I2,I3,S0,S1;
output Y;
wire P,Q,R,S,S0c,S1c;
not(S0c,S0);
nor(S1c,S1);
and (P,S0c,S1c,I0);
and(Q,S0c,S1,I1);
and(R,S0,S1c,I2);
and(S,S0,S1,I3);
or(Y,P,Q,R,S);
endmodule

## De-multiplexer
module ex07(Y0,Y1,Y2,Y3,S0,S1,I);
input I,S0,S1;
output Y0,Y1,Y2,Y3;
wire S0c,S1c;
not(S0c,S0);
nor(S1c,S1);
and (Y0,I,S0c,S1c);
and(Y1,I,S0c,S1);
and(Y2,I,S0,S1c);
and(Y3,I,S0,S1);


```

### RTL LOGIC  

Multiplexer :

![exp7](https://user-images.githubusercontent.com/94506182/200120639-91c94240-235c-4372-b175-f073926989eb.png)

De-multiplexer :

![E7 2](https://user-images.githubusercontent.com/94506182/200120680-a81f079f-8ce4-4152-a58b-0da67c373c7f.png)



### TIMING DIGRAMS  
Multiplexer WHEN I0=1
![T1](https://user-images.githubusercontent.com/94506182/200120770-5bcd8773-1d3e-41db-ba5e-fe63745d2d04.png)
WHEN I1=1
![T2](https://user-images.githubusercontent.com/94506182/200120822-44ff6801-2e2b-4246-9f9b-10f2ccde47a9.png)
WHEN I2=1
![T3](https://user-images.githubusercontent.com/94506182/200120884-90baba6f-fdf6-4c66-85a5-dea5749ca078.png)
WHEN I3=1
![T4](https://user-images.githubusercontent.com/94506182/200120931-70aa71b7-0917-4ee6-b4ac-a3178ba86a35.png)
De-multiplexer :
![T5](https://user-images.githubusercontent.com/94506182/200121004-7a1b0c1b-2f91-4c19-bb7b-d33d55ba835d.png)
![T8](https://user-images.githubusercontent.com/94506182/200121065-48879ce1-e954-4d63-bbb4-93867973f5b1.png)

De-multiplexer :
![T9](https://user-images.githubusercontent.com/94506182/200121124-fd2bcaa2-66d0-4b74-906a-d311119492c8.png)





### RESULTS 
4 X1 multiplexer and 1X4 de multiplexer has been implemented using verilog and outputs are
validated.
