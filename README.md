KT0915_DSP_RADIO-fullscreen-info
================================

Arduino source for KT0915 Software Radio with full-screen (1.8inch SPI Color LCD) interface, capable of reception for LW, MW, SW, FM and Air Band (Avion).  

Air band reception is not perfect due to mode difference (FM to AM), but you will hear some ACARS signal and GND/TWR calling.   

Shortwave station information should be prepared by timetable.h, and FM by fmstation.h.  

In this update, I added air_station.h which include avion stations. Please edit for your local stations.  

To complete this radio,  
KT0915 chip,  
Arduino UNO (or ATMega328P, 168 is not enough to accomodate.),  
SPI 1.8inch ST7735 module,   
rotary encorder and band switch.  

Connection to LCD is same as Arduino TFT.h sample, and   
rotary encorder should be connected to D2, D4,  
band switch to D3,  
and KT0915 and DS1307-RTC to I2C network.  

It should be noted that KT0915 is NOT 5V tolerant, and DS1307 does not work at Vcc=3.3V.  
You can avoid simply 3.3V-pull up I2C network with Vcc=3.3V to KT0915 and Vcc=5V to DS1307. (You don't need level converter just for DS1307).  

RTC related two libraries is required to use RTC  
(http://www.pjrc.com/teensy/arduino_libraries/Time.zip ,  
http://www.pjrc.com/teensy/arduino_libraries/DS1307RTC.zip )  

An example of implementation can be found in http://blogs.yahoo.co.jp/le_nozze_di_figaro_2001/38170502.html  
As far as PLL locks, this wonderful IC can receive signal, indeed not limited to broadcast frequency.  
Enjoy listening!  
