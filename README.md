# Negative pressure wound therapy (NPWT)

## <p> Project layout </p> 
1. [Introduction](https://github.com/moaml1999/NPWT#introduction) : <p> explanation of wound healing and the method of wound healing by negative pressure.</p>
2. [Hardware](https://github.com/moaml1999/NPWT#hardware) : <p> discuss the materials used in the design of this project theoretically & the hardware parts we used in this project with a simple explanation of each part.</p> 
3. [Software](https://github.com/moaml1999/NPWT#software) : <p>explained here the software program to write codes and platforms used to control the device that connect device with internet.</p>


# Introduction
<p> Wound healing is a complex biological process consisting of hemostasis, inflammation, proliferation, and remodeling. Large numbers of cell types including neutrophils, macrophages, lymphocytes, keratinocytes, fibroblasts, and endothelial cells are involved in this process. Multiple factors can impair wound healing by affecting one or more stages of the process and are categorized into local and systemic factors. The effects of these factors are not mutually exclusive. Single or multiple factors may play a role in any one or more individual stages, contributing to the overall outcome of the healing process.
Negative pressure wound therapy (NPWT) is a method of drawing fluid and infection out of a wound to help it heal. A special dressing (bandage) is sealed over the wound and a gentle suction pump is attached.
Negative pressure wound therapy (NPWT), also called vacuum-assisted wound closure, refers to wound dressing systems that continuously or intermittently apply subatmospheric pressure to the system, delivering positive pressure to the wound surface. NPWT has become a popular treatment modality for the management of many acute and chronic wounds. Subatmospheric pressure has multiple beneficial effects on wound healing in animal models. </p>


# Hardware
## 1-	ESP32
<p>ESP32 is a series of low-cost, low-power system on a chip microcontrollers with integrated Wi-Fi and dual-mode Bluetooth. The ESP32 series employs either a Tensilica Xtensa LX6 microprocessor in both dual-core and single-core variations, Xtensa LX7 dual-core microprocessor or a single-core RISC-V microprocessor and includes built-in antenna switches, RF balun, power amplifier, low-noise receive amplifier, filters, and power-management modules. ESP32 is created and developed by Espressif Systems, a Shanghai-based Chinese company, and is manufactured by TSMC using their 40 nm process. It is a successor to the ESP8266 microcontroller.
The board which I have has 30 Pins (15 pins on each side). There are some board with 36 Pins and some with slightly less Pins.</p>
 
 ![ESP32 Board consists](https://github.com/moaml1999/NPWT/blob/main/images/ESP32.jpg) 
   
<p> Fig 1 the ESP32 Board consists </p>

<p> As you can see from Fig 1, the ESP32 Board consists of the following: </p>

-	ESP-WROOM-32 Module
-	Two rows of IO Pins (with 15 pins on each side)
-	CP2012 USB – UART Bridge IC
-	micro–USB Connector (for power and programming)
-	AMS1117 3.3V Regulator IC
-	Enable Button (for Reset)
-	Boot Button (for flashing)
-	Power LED (Red)
-	User LED (Blue – connected to GPIO2)
-	Some passive components

<p>Features: </p>

-	Single or Dual-Core 32-bit LX6 Microprocessor with clock frequency up to 240 MHz.
-	520 KB of SRAM, 448 KB of ROM and 16 KB of RTC SRAM.
-	Supports 802.11 b/g/n Wi-Fi connectivity with speeds up to 150 Mbps.
-	Support for both Classic Bluetooth v4.2 and BLE specifications.
-	34 Programmable GPIOs.
-	Up to 18 channels of 12-bit SAR ADC and 2 channels of 8-bit DAC
-	Serial Connectivity include 4 x SPI, 2 x I2C, 2 x I2S, 3 x UART.
-	Ethernet MAC for physical LAN Communication (requires external PHY).
-	1 Host controller for SD/SDIO/MMC and 1 Slave controller for SDIO/SPI.
-	Motor PWM and up to 16-channels of LED PWM.


## 2-	AS21 Pressure Sensor Module
<p> AS21 is a prefect silicon pressure sensor module offering a ratiometric analog interface for reading pressure over the specified full scale pressure span and temperance. The AS21 incorporates a silicon piezoresistive pressure sensor and an on-board Application Specific Integrated Circuit (ASIC) under PC board in a DIP6 package. The AS21 is fully calibrated and temperature compensated for offset, sensitivity, temperature and non-linearity,soAS21 pressure sensor module satisfy the prefect repeatability, linearity, stability and sensibility, which can be applied directly in medical equipment, fitness machine, home electronics, and other pneumatic devices etc. AS21 pressure sensor module is for high volume application at an affordable cost and perfect performance. Customized calibrations (working voltage, output voltage, and pressure range) are available.</P>

 ![Pressure Sensor Module](https://github.com/moaml1999/NPWT/blob/main/images/pressure_sensor.jpg) 

<p>  Fig 2 Pressure Sensor Module </p>


<p> Features:</p>

-	Ranges:-100kPa～0kPa…1500kPa(-15PSI～0PSI…225PSI) 
-	Optional 5V or 3.3V or 3V power supply 
-	Gage & Vacuum Type ■ For Non-corrosive gas or air 
-	Calibrated Amplified Analog signal or Digital output 
-	Temp. Compensated:0℃～+60℃(32℉～+140℉) 
-	Direct application, Low Cost.
 
![AS21 Pressure Sensor Module pins](https://github.com/moaml1999/NPWT/blob/main/images/pressure_sensor_pins.jpg) 

<p> Fig 3 AS21 Pressure Sensor Module pins </p>

## 3-	Air Pump
Mini electric vacuum pump with high air flow for good performance.Vacuum pump is made of premium aluminium and plastic, it is corrosion resistant and durable in use. Mini size design of pump, with inlet and outlet on its body. Electric air pump is easy to install, provide much convenience. Air pressure pump is widely used in air sampling, instruments and equipment and industry, home appliances and other fields.

![air pump](https://github.com/moaml1999/NPWT/blob/main/images/pump.jpg) 

<p> Fig 4 air pump </p>

<P> Features:</P>

-	Delicate appearance, small size, long life.
-	Low noise, high quality efficiency, zero crosstalk.
-	High torque, high precision.
-	Energy-saving and mute.
-	Save electricity and low heat.
-	Light weight, easy installation.

## 4-	 I2C LCD 16x2 screen display
<p class="text-justify" > LCD modules are very commonly used in most embedded projects, the reason being its cheap price, availability and programmer friendly. Most of us would have come across these displays in our day-to-day life, either at PCO’s or calculators. The appearance and the pinouts have already been visualized above now let us get a bit technical. 16×2 LCD is named so because; it has 16 Columns and 2 Rows. There are a lot of combinations available like, 8×1, 8×2, 10×2, 16×1, etc. but the most used one is the 16×2 LCD. So, it will have (16×2=32) 32 characters in total and each character will be made of 5×8 Pixel Dots. </p>

![I2C LCD 16x2 screen](https://github.com/moaml1999/NPWT/blob/main/images/lcd_i2c.jpg) 

<p> Fig 5 I2C LCD 16x2 screen </p>

# Software 
## 1-  Arduino IDE 
<p> Arduino IDE is an open source software that is mainly used for writing and compiling the code into the Arduino Module. It is official Arduino software, making code compilation too easy that even a common person with no prior technical knowledge can get their feet wet with the learning process. It is easily available for operating systems like MAC, Windows, Linux and runs on the Java Platform that comes with inbuilt functions and commands that play a vital role for debugging, editing and compiling the code in the environment. A range of Arduino modules available including Arduino Uno, Arduino Mega, Arduino Leonardo, Arduino Micro and many more.  Each of them contains a microcontroller on the board that is actually programmed and accepts the information in the form of code. The main code, also known as a sketch, created on the IDE platform will ultimately generate a Hex File which is then transferred and uploaded in the controller on the board.  The IDE environment mainly contains two basic parts: Editor and Compiler where former is used for writing the required code and later is used for compiling and uploading the code into the given Arduino Module. This environment supports both C and C++ languages.</p> 

## 2-  Blynk 
<p> Blynk is an internet of things platform which allows controlling electronic devices remotely using its iOS and android apps. It provides dashboard by which user can create graphic interface using different widgets. Blynk can also store and display sensor data. Blynk provides libraries for most of the popular hardware platforms like Arduino, ESP8266 , Raspberry pi, SparkFun etc.
In the Blynk three most important components are App, Server and Libraries. App can help to create the interface. Server is responsible for all the communication between app and the hardwires. And Libraries enables communication for hardware with the server using commands.</p>
 
Getting Started With The Blynk App
1. Create a Blynk Account
2. Create a New Project
3. Choose Your Hardware
4. Auth Token
5. Add a Widget
6. Run the Project
