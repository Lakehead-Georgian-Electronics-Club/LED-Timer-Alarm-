# LED-Timer-Alarm

#### Intro:  
Everybody uses alarms, obviously right but, everyone has definitely had an experience where the alarm hasn’t woken them up. My phone has a maximum decibel rating of 100 db. My piezo buzzer can go up to 115 db . Also, it is a sound I'm not used to and I can always change the pattern of buzzes so we keep it fresh. I’m also very extra about these sorts of gadgets so why not be able to also visualize the time rather than a sound because that's more of a mental reminder? Reading this I now feel as if an alarm clock is a very specific use for this device whereas a timer or time-keeping device is more of a general application that can be programmed to be an alarm clock so let’s do that.

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
     
     // Here is where the magic happens and the Timer / Alarm is programmed . Improvements include using the Serial.io functions to be able to change alarm using keypad .
     
     // keeps pin on for 60 minutes or 1 hour  each unit is equal to 1 ms , this is where you can program the time
    // possible improvements include using pins as input to manually control the timer length , add even more lights so it is hard to ignore and display timer using led matrix or 7 segment display  . Could also create a custom alarms using speakers.
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
     digitalWrite(Buzzer,HIGH);
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
