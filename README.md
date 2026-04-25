
![License](https://img.shields.io/badge/License-MIT-blue.svg)
![Hackatime Badge](https://hackatime-badge.hackclub.com/U0A2SJ7B739/Resolution%20week%203)


# 14-Bit Binary Ripple Counter using IC

## The main idea

After looking for examples on Google, I had the idea to make like a **Binary counter with LEDs**. I am going to use an ***NE555*** and ***CD4020***. It's bacically binary logic and clock generation using classic **CMOS and Timer integrated circuits**. The NE555 is configured in astable mode and act as the system's heartbeat. The CD2040 receive the clock pulses and each stage of the counter **divides the frequency** of the previous one by two. By adding LEDs, we can create a **visual representation** of binary increments.

## Features
***Visual Feedback*** : 12 LEDs displaying the counting sequence from $2^0$ to $2^{13}$.  
***Manual Reset*** : A dedicated switch to clear the counter and restart from ``` 00000000000000 ```.

## Main Components

| Component | Function |
| ------------- | ------------- |
| NE555P  | Precision Timer (Clock Source)|
| CD4020B  | 14-Stage Binary Ripple Counter |
| LEDs  | Output indicators for each binary stage |

## Technical Specifications  
<ins> Following the datasheets, these are the specs :</ins>   

***Supply Voltage*** : 5V to 12V DC. We will use 9V  
***Logic Level*** : CMOS.  
***Architecture*** : Asynchronous (Ripple) Counter.

## Wiring diagram 



### Wiring from [instructable](https://www.instructables.com/LED-cube-using-4020-Ic-and-555-IC/) 


<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/ec23ec08-f0db-4b34-a4e9-b48f119133e8" />
<br>

### My wiring on [Falstad](https://is.gd/O34XgH) 
<br>

<img src="https://github.com/user-attachments/assets/d72ed655-9647-4156-816a-199e91de24b4" width=50%>






## My changes

I changed the instructable connections by having just 12 LEDs to represent the **14 stages the CD4020 has**. I also added a switch between R and +12V to have the possibility to **reset the circuit anytime** ! In the screenshot, the circuit has a 56nF capacitor (really small) to accelerate the process as Falstad is not using real time simulation.  

For the real circuit, I'll be using 4.7uF for the whole thing to last aprox **10 minutes**. And to easily calibrate everything, I'll also be using +9V instead of +12V
<br>  

## Schematic and PCB

### Schematic on KiCad

<img width="1210" height="836" alt="image" src="https://github.com/user-attachments/assets/b7f0c6ba-5668-4d20-8305-05f8c41fbeff" />  
<br>

> I used the Falstad's diagram I previously showed to make this schematic. 
<br>

### PCB on KiCad
<br>
<div align=center>
 <img width=60% alt="Capture d&#39;écran 2026-04-15 120002" src="https://github.com/user-attachments/assets/072f2ca3-4444-468c-bc1b-57da9dab0483" />
<br>  
<br>
First step of the PCB, with all components correctly arranged and a GND pour around the LEDs
</div>

<br>

### Silckscreen on KiCad

<div align=center>
 <table>
  <tr>
   <td valign=bottom><img width=80% alt="Capture d&#39;écran 2026-04-12 010734" src="https://github.com/user-attachments/assets/783825f2-2362-49f4-96b6-fe6d9004dc31" /></td>
<td valign=bottom><img width=90% alt="Capture d&#39;écran 2026-04-15 120036" src="https://github.com/user-attachments/assets/90abdd68-19da-418d-9e1e-4a76a391949d" /></td>
<td valign=bottom><img width=100% alt="Capture d&#39;écran 2026-04-15 120015" src="https://github.com/user-attachments/assets/017aed8c-4339-49ad-8ef7-d41160465f26" /></td>
  </tr>
 </table>
</div>


Each LED represents a specific **power of 2** in the binary system. To find the current decimal value of the counter, simply **add up the values** of all the LEDs that are **currently turned on**.
<br>
It goes from 1 to 8 because the 2nd and 3rd stage of the CD4020 have no output to show on a LED. However, the **time is still respected** as the stage are well here.

