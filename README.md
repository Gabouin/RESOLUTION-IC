# RESOLUTION-IC

## The main idea

After looking for examples on Google, I had the idea to make like a **Binary meter with LEDs**. I am going to use an ***NE555*** and ***CD4020***. It's bacically binary logic and clock generation using classic **CMOS and Timer integrated circuits**. The NE555 is configured in astable mode and act as the system's heartbeat. The CD2040 receive the clock pulses and each stage of the counter **divides the frequency** of the previous one by two. By adding LEDs, we can create a **visual representation** of binary increments.

## Features
***Visual Feedback*** : 14 LEDs displaying the counting sequence from $2^0$ to $2^{13}$.  
***Manual Reset*** : A dedicated switch to clear the counter and restart from ``` 00000000000000 ```.

## Main Components

| Component | Function |
| ------------- | ------------- |
| NE555P  | Precision Timer (Clock Source)|
| CD4020B  | 14-Stage Binary Ripple Counter |
| LEDs  | Output indicators for each binary stage |

## Technical Specifications  
<ins> Following the datasheets, these are the specs :</ins>   

***Supply Voltage*** : 5V to 12V DC.  
***Logic Level*** : CMOS.  
***Architecture*** : Asynchronous (Ripple) Counter.

## Wiring diagram 



### wiring from [instructable](https://www.instructables.com/LED-cube-using-4020-Ic-and-555-IC/)  



<img width="1145" height="782" alt="image" src="https://github.com/user-attachments/assets/ec23ec08-f0db-4b34-a4e9-b48f119133e8" />

> 



### my wiring on [Falstad](https://is.gd/O34XgH)   


<img width="736" height="537" alt="image" src="https://github.com/user-attachments/assets/bd9257d2-8099-42d3-96d2-e900cc0843c4" />


![IC](https://github.com/user-attachments/assets/d72ed655-9647-4156-816a-199e91de24b4)





## My changes

I changed the instructable connections by having just 14 LEDs to represent the **14 stages the CD4020 has**. I also added a switch between R and +12V to have the possibility to **reset the circuit anytime** ! In the screenshot, the circuit has a 56nF capacitor (really small) to accelerate the process as Falstad is not using real time simulation.  

For the real circuit, I'll be using 4.7uF for the whole thing to last aprox **10 minutes**.

