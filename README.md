# arduino_esp8266
Send data from an arduino, via wifi to update a thingspeak graph
I used the following:
- Arduino UNO board
- 3.3 volt regulator (TS1086)
- ESP8266 (Version 1)
- Breadboard
- 1k and 2.2k resistors (to divide voltage from 5v to 3.3v for the RX line)
- Jumper wires

Connections to the Arduino board are
- Ground      -> Ground of ESP8266
- Pin 11 (TX) -> resistor dividor top (1K)
- Pin 10 (RX) -> TX of ESP8266

Connections of separate 5V power supply
- ground   - pin 1 of TS1086 -> Ground for ESP8266 (See above for link back to Ground of Arduino)
- 5V in    - pin 3 of TS1086
             pin 2 of TS1086 -> 3.3V for ESP8266

Connections for the ESP8266 (only 5 wires needed)
- TX     -> Arduino pin 10
- RX     -> Resistor network mid point
- 3.3V   -> pin 2 of TS1086
- Ground -> Ground of Arduino
- CH_PD  -> 3.3V 

Connections for resistor network
- Resistor network top (1K) -> Pin 11 (TX) of Arduino
- Resistor network middle   -> RX pin of ESP8266
- Resistor network bottom   -> Ground of Arduino

N.B. You also need to set up a thingspeak account and use the api key 