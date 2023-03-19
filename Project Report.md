# LED-Timer-Alarm

#### Intro:  
Everybody uses alarms, obviously right but, everyone has definitely had an experience where the alarm hasn’t woken them up. My phone has a maximum decibel rating of 100 db. My piezo buzzer can go up to 115 db . Also, it is a sound I'm not used to and I can always change the pattern of buzzes so we keep it fresh. I’m also very extra about these sorts of gadgets so why not be able to also visualize the time rather than a sound because that's more of a mental reminder? Reading this I now feel as if an alarm clock is a very specific use for this device whereas a timer or time-keeping device is more of a general application that can be programmed to be an alarm clock so let’s do that.
'


      #define Buzzer 13

      byte ledPins[] = {15, 2, 0, 4, 5, 18, 19, 21, 22, 23}; /// for the operation of led lights

      int ledCounts; // For the upper bounds of for loop

      void setup()

     {
       ledCounts = sizeof(ledPins); // sets up the upper bound of for loop
       for (int i = 0; i < ledCounts; i++)
       {
         pinMode(ledPins[i], OUTPUT);// pin function(led Group) to determine wht the pins are used for
         pinMode( Buzzer ,OUTPUT);// pin function for piezo buzzer , Nickname : Buzzer
       }


     }


     void loop() //keep looping unit exit is programmed in
 
     {
       for (int i = 0; i < ledCounts; i++) //starts at 0 ( 1st postition in array ) this loop has the led bar bar add increments as time runs on
       {  
          delay(60*1000*60);  
     
       // Here is where the magic happens and the Timer / Alarm is programmed . Improvements include using the Serial.io functions to be able to change alarm using             keypad .
     
     // keeps pin on for 60 minutes or 1 hour  each unit is equal to 1 ms , this is where you can program the time
    // possible improvements include using pins as input to manually control the timer length , add even more lights so it is hard to ignore and display timer using        led matrix or 7 segment display  . Could also create a custom alarms using speakers.
       // Can use buttons for to control inputs
   
     digitalWrite(ledPins[i], HIGH); // turns on pin
     digitalWrite(Buzzer,HIGH); // turns on the buzzer
     delay(1000);// waits for 1 second before the next comand keeping buzzer on until then
     digitalWrite(Buzzer,LOW);
     delay(100); // have to include delay in between because the microcontroller is fast , literally almost lightspeed.
     digitalWrite(Buzzer,HIGH);
     delay(100);
     digitalWrite(Buzzer,LOW);   /// random buzz pattern for fun
     delay(100);
     digitalWrite(Buzzer,HIGH);   // code improvement includes using Function to randomize beep pattern / shorten code
     delay(100);
     digitalWrite(Buzzer,LOW);
     delay(100);
     digitalWrite(Buzzer,HIGH);
     delay(1000);
     digitalWrite(Buzzer,LOW);
     }


     for (int i = ledCounts - 1; i > -1; i--) {
     digitalWrite(ledPins[i], LOW); // turns off all leds
     }


     }
     }
     
<img width="1500" alt="CIrcuit diagram" src="https://user-images.githubusercontent.com/117550153/226148229-6fe6dc8a-8d85-4dfe-a726-77c883867bff.png">
<img width="1500" alt="livepic" src="https://user-images.githubusercontent.com/117550153/226148326-ded2702d-c7fc-4f79-b3d0-c9e957c9c762.png">



#### Description :  


This project was made using the ESP32-WROVER chip. The function of this project is to act as a timer or an alarm. A 115-decibel ( unit for sound intensity )  sound is the maximum from the piezo buzzer compared to my phones 100 decibel maximum sound ( for reference 110 decibels is about 10 times as loud as 100 decibels due to the log scale that is used to measure sound intensity . ) So personally, this device is more preferable than any alarm my phone can produce, especially when the pattern of buzzes are programmable which can help to avoid the brain from tuning out after using a specific sound for too long. The timer works based on the internal clock of the chip, with a minimum charge of an interval to be 1 millisecond, so this timer can be pretty accurate. A led bar is included as a visual aid to determine how far the programmed time is with 10 visual intervals(Leds). The Buzzer is currently programmed above to buzz after every interval ( Timer mode ) but can be programmed to buzz once at the end ( Alarm mode). Time intervals do not have to be equal for extra freedom in the programming of devices.





#### Skills demonstrated : 


-Basic understanding of Microcontroller chip 

-Basic understanding of C coding language 

-Basic understanding of passive/active electrical components

