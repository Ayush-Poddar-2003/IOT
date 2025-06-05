# INTERFACE 
An interface is a way for two devices to communicate.   
Raspberry Pi supports multiple types of interfaces through its GPIO (General Purpose Input/Output) pins. 

1. SERIAL   
UART - Universal Asynchronous Receiver/Transmitter  
**Used for** : Simple 1 to 1 communication between Pi and another device  
**Wires used**: TX (Transmit), RX (Receive), GND.  
**Speed**: Slower, simple setup.  
**Example**: Sending data from a GPS sensor to the Pi.  

2. SPI   
Serial peripheral interface  
**Used for:** Fast communication with multiple slave devices (e.g., ADC chips, displays).  
**Speed**: Fast, full-duplex.   
**Wires used:**  
    • MISO (Master In Slave Out)  
    • MOSI (Master Out Slave In)  
    • SCLK (Clock)  
    • CE0/CE1 (Chip Enable lines)  


3. I2C    
**Used for**: Communicating with multiple low speed devices using 2 wires.  
**Wires used**: SDA (Data), SCL (Clock)  
Devices are addressed using unique addresses.  
**Example**: Reading temperature from a 
sensor.