# Timer_Driver

Using three modes timer ( Timer0 , Timer1 , Timer2) . 

Timer0 :-

Load TCNT0 with 0x00
Set CS00 and CS02 bits in TCCR0 register. This will start the timeWe will calculate the tick time in just a moment.r at Clk/1024 speed.
Monitor the TOV0 flag in the TIFR0 register to check if the timer has over-flowed, keep a timerOverFlowCount.
If timerOverFlowCount >= 6,for example toggle the led on PD4 and reset the count

Timer1 :-

The Timer 1 is 16 bit, that means it can count from 0 to $$2^{16} = 65536$$. Hence the Timer/Counter 1 is a 16 bit registered formed out of TCNT1H and TCNT1L as shown below.

Timer2 :-

Timers are independent units from the CPU. Hence if we use timers with Interrupts it can make the CPU free from polling the flags every-time. This is the way they are used normally.
