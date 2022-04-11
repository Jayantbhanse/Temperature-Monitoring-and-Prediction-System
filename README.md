# Temperature-Monitoring-and-Prediction-System
We can predict the temperature in the room where the bolt iot module connected to LM35 IC (Temperature sensor) with the help of polynomial regression.

COMPONENTS USED –

Bolt Wi-Fi Module
LM35 IC (temperature sensor)
Bolt cloud
Jumper wires
 

Hardware setup-



Step 1: Hold the sensor in a manner such that you can read LM35 written on it.

Step 2: In this position, identify the pins of the sensor as VCC, Output and Gnd from your left to right.

Step 3: Using male to female wire connect the 3 pins of the LM35 to the Bolt Wifi Module as follows:

VCC pin of the LM35 connects to 5v of the Bolt Wifi module.
Output pin of the LM35 connects to A0 (Analog input pin) of the Bolt Wifi module.
Gnd pin of the LM35 connects to the Gnd.
 



SETTING UP BOLT WIFI MODULE

Setting up the Bolt wifi module 
Creating a product - In this project since we are using the A0 pin as an input pin and we are collecting the data over GPIO so choose the Input Devices and GPIO while creating the product. 
Link your device to the product


Code-

Code for monitoring and predicting room temperature

setChartLibrary('google-chart');

setChartTitle('Polynomial Regression');

setChartType('predictionGraph');

setAxisName('time_stamp','temp');

mul(0.0977);

plotChart('time_stamp','temp');

//end of code








mul in the code is multiplication factor

T=r/10.24

 

Where T is the temperature in degrees Celsius, and r is the ADC value. This formula reduces to the following formula.

T=r*0.0977

The mul function in the above code multiplies a constant to every data point retrieved from the Cloud, before plotting the data points. This is necessary to convert the recorded ADC values into temperature reading in degrees Celsius.

