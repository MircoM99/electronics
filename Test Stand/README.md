# ARCHIE
> Electronic Board for Test Stand Development of the THRUST Student Project.

ARCHIE is a ESP32 based data logging and actuation capable system that is able to record and control 
* 4 Thermocouples channels, 
* 3 Pressure Sensors channels, 
* 3 Mosfet Actuated Electrovalve channels 
* 1 Load Cell channel. 



<p align="center">
  <img src="https://github.com/thrust-team/electronics/blob/main/Test%20Stand/Figures/TSPCB_Front_Tilt.PNG" width="300" height = "600" />
  <img src="https://github.com/thrust-team/electronics/blob/main/Test%20Stand/Figures/TSPCB_Back_Tilt.PNG" width="300" height = "600"/> 
</p>

## MCU


## Temperature
Temperature information are supplied by the four indipendent thermocouples channel that are powered by the [Adafruit MAX 31856 Board](https://www.adafruit.com/product/3263). This Breakout is capable of reading temperature measurement from all type of thermocouples thanks to the [MAX 31856](https://datasheets.maximintegrated.com/en/ds/MAX31856.pdf) integrated chip. 

## Pressure
Pressure datas are supplied by 4-20mA Pressure transducer. This type of sensor can be easily read by the [Adafruit ADS1115](https://www.adafruit.com/product/1085) ADC thanks to a simple 200 Ohms resistor that provides a range of voltages from 0.8V (4mA) to 4V (20mA) to the ADC. Any 4-20mA sensor can actually be connected to these channels. 

## Force


## Electrovalves

## Power

