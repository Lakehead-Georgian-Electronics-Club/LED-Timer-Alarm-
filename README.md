# LED-Timer-Alarm


## Intro:  
Everybody uses alarms, obviously right but, everyone has definitely had an experience where the alarm hasn’t woken them up. My phone has a maximum decibel rating of 100 db. My piezo buzzer can go up to 115 db . Also, it is a sound I'm not used to and I can always change the pattern of buzzes so we keep it fresh. I’m also very extra about these sorts of gadgets so why not be able to also visualize the time rather than a sound because that's more of a mental reminder? Reading this I now feel as if an alarm clock is a very specific use for this device whereas a timer or time-keeping device is more of a general application that can be programmed to be an alarm clock so let’s do that.

 

## Description :  


This project was made using the ESP32-WROVER chip. The function of this project is to act as a timer or an alarm. A 115-decibel ( unit for sound intensity )  sound is the maximum from the piezo buzzer compared to my phones 100 decibel maximum sound ( for reference 110 decibels is about 10 times as loud as 100 decibels due to the log scale that is used to measure sound intensity . ) So personally, this device is more preferable than any alarm my phone can produce, especially when the pattern of buzzes are programmable which can help to avoid the brain from tuning out after using a specific sound for too long. The timer works based on the internal clock of the chip, with a minimum charge of an interval to be 1 millisecond, so this timer can be pretty accurate. A led bar is included as a visual aid to determine how far the programmed time is with 10 visual intervals(Leds). The Buzzer is currently programmed above to buzz after every interval ( Timer mode ) but can be programmed to buzz once at the end ( Alarm mode). Time intervals do not have to be equal for extra freedom in the programming of devices.





#### Skills demonstrated : 


-Basic understanding of Microcontroller chip 

-Basic understanding of C coding language 

-Basic understanding of passive/active electrical components
