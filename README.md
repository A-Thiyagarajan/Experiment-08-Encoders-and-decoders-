# Experiment-08- Encoders-and-decoders 
## AIM: 
To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
## HARDWARE REQUIRED:  
PC, Cyclone II , USB flasher
## SOFTWARE REQUIRED:  
Quartus prime
## THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
#### Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
#### Figure -02 3 to 8 Encoder implenentation 

## Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
#### Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
#### Figure -04 8 to 3 Decoder implementation 

## Procedure

Step1:- Open the quartus II software.

Step2:- Create a new project.

Step3:- Name the projects such that the same name is used for mentioning the name of the module.

Step4:- Develop programmes for both Encoder and Decoder using verilog programming.

Step5:- Run RTL Simulation.

Step6:- Create the Timing diagram.

Step7:- Validate the outputs.



## PROGRAM 
```
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: A.Thiyagarajan
RegisterNumber:  22008681
i)ENCODER:
module exp8(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule

ii)DECODER:
module dec(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
output d0,d1,d2,d3,d4,d5,d6,d7;
input a,b,c;
assign d0=(~a & ~b & ~c) ;
assign d1=(~a & ~b &c);
assign d2=(~a & b &~c);
assign d3=(~a & b &c);
assign d4=(a &~b&~c);
assign d5=(a &~b&c);
assign d6=(a&b&~c);
assign d7=(a&b&c);
endmodule

```




## RTL LOGIC  

### Encoder
![encoder ](https://user-images.githubusercontent.com/118707693/212561859-b547110d-4e8c-4a10-9d55-ab9d87b97db2.png)


### Decoder

![decoder](https://user-images.githubusercontent.com/118707693/212561862-91f22c99-7d1b-428e-b326-ce8c1a0690bd.png)


## TIMING DIGRAMS  

### Encoder
![encoder td 1](https://user-images.githubusercontent.com/118707693/212561870-05e185ee-5cd7-49c5-8a48-e2380ed7f28e.png)

![encoder td 2](https://user-images.githubusercontent.com/118707693/212561873-cc60ec08-3ce5-4397-a30e-a4347745b2e3.png)

![encoder td 3](https://user-images.githubusercontent.com/118707693/212561876-b2a40ee0-05eb-482c-9dd0-4b62c8eefea4.png)

### Decoder

![decoder td ](https://user-images.githubusercontent.com/118707693/212561886-b35f90c3-d294-4458-b90c-925b765d6eb8.png)



## TRUTH TABLE 

### Encoder

![encoder truth table](https://user-images.githubusercontent.com/118707693/212561895-bfe8e527-e3ab-45bd-91d1-598896facd4d.png)

### Decoder

![decoder truth table](https://user-images.githubusercontent.com/118707693/212561897-96136f21-0493-4a99-80eb-9787030afb97.png)





## RESULTS 
Thus 8 to 3 Encoder and 3to8 Decoder are implemented successfully using verilog and validate its outputs.


