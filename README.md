# 12-Bit Binary Ripple Counter using IC

## The main idea

After looking for examples on Google, I had the idea to make like a **Binary meter with LEDs**. I am going to use an ***NE555*** and ***CD4020***. It's bacically binary logic and clock generation using classic **CMOS and Timer integrated circuits**. The NE555 is configured in astable mode and act as the system's heartbeat. The CD2040 receive the clock pulses and each stage of the counter **divides the frequency** of the previous one by two. By adding LEDs, we can create a **visual representation** of binary increments.

## Features
***Visual Feedback*** : 12 LEDs displaying the counting sequence from $2^0$ to $2^{11}$.  
***Manual Reset*** : A dedicated switch to clear the counter and restart from ``` 00000000000000 ```.

## Main Components

| Component | Function |
| ------------- | ------------- |
| NE555P  | Precision Timer (Clock Source)|
| CD4020B  | 12-Stage Binary Ripple Counter |
| LEDs  | Output indicators for each binary stage |

## Technical Specifications  
<ins> Following the datasheets, these are the specs :</ins>   

***Supply Voltage*** : 5V to 12V DC. We will use 9V  
***Logic Level*** : CMOS.  
***Architecture*** : Asynchronous (Ripple) Counter.

## Wiring diagram 



### Wiring from [instructable](https://www.instructables.com/LED-cube-using-4020-Ic-and-555-IC/) &emsp; &emsp; &emsp; &emsp; &emsp; &emsp; &emsp; &emsp; &emsp; &emsp; &emsp; My wiring on [Falstad](https://is.gd/O34XgH) 



<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/ec23ec08-f0db-4b34-a4e9-b48f119133e8" />
<img width="500" height="420" alt="image" src="https://github.com/user-attachments/assets/bd9257d2-8099-42d3-96d2-e900cc0843c4" />

<br>
<br>

&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; ![IC](https://github.com/user-attachments/assets/d72ed655-9647-4156-816a-199e91de24b4)





## My changes

I changed the instructable connections by having just 12 LEDs to represent the **12 stages the CD4020 has**. I also added a switch between R and +12V to have the possibility to **reset the circuit anytime** ! In the screenshot, the circuit has a 56nF capacitor (really small) to accelerate the process as Falstad is not using real time simulation.  

For the real circuit, I'll be using 4.7uF for the whole thing to last aprox **10 minutes**. And to easily calibrate everything, I'll also be using +9V instead of +12V
<br>  

## Schematic and PCB

### Schematic on KiCad

<img width="1210" height="836" alt="image" src="https://github.com/user-attachments/assets/b7f0c6ba-5668-4d20-8305-05f8c41fbeff" />  
<br>
<br>


> I used the Falstad's diagram I previously showed to make this schematic. 
<br>

### PCB on KiCad

&emsp; &emsp;&emsp;&emsp; &emsp;&emsp; &emsp;&emsp; &emsp; &emsp; <img width="624" height="574" alt="image" src="https://github.com/user-attachments/assets/7ea49f24-dde2-49f5-a9ca-5df63caa7c0d" />  
> First step of the PCB, with all components correctly arranged and a GND pour around the LEDs
<br>


# LICENCE 

MIT License

Copyright (c) 2026 Gabin Tavernier

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.






