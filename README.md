***House Safeguard System***

![图片1](https://user-images.githubusercontent.com/113784775/209004233-22f891a7-03af-438c-8b33-9763c051c810.png)


# Overview

House safeguard system is an effective measure to solve the security management at the entrance and exit of important departments. Applicable to various confidential departments, such as banks, hotels, parking lot management, computer rooms, factories, etc.

This system equipped with a camera can capture the image of the visitor and remind the user the identification of the intruder coming in the building.

![9468d6a5488b16e94c7766e25f1e825](https://user-images.githubusercontent.com/113784775/209005894-b024bc01-262d-42ec-a37d-ac682358e78c.jpg)

# Instruction

## Components

### Pico4ml

![205468396-f7646e87-75a1-4214-ab9a-8d6017183e20](https://user-images.githubusercontent.com/113784775/209006169-25bd133d-46ec-4a9b-950c-a0bd813b3cc2.jpg)

Amazon: https://www.amazon.com/Arducam-Pico4ML-TinyML-RP2040-Onboard/dp/B0919KQ7NV

### HC-05 Bluetooth

![image](https://user-images.githubusercontent.com/113784775/209006518-f7730e44-179e-439b-9c0a-ea14ad34d1f7.png)

Amazon: https://www.amazon.com/HiLetgo-Wireless-Bluetooth-Transceiver-Arduino/dp/B071YJG8DR

### VGA Cable

![image](https://user-images.githubusercontent.com/113784775/209006745-9724eaf8-04a6-460d-82e7-4cf86547dd45.png)

Amazon: https://www.amazon.com/Pasow-Monitor-Cable-Computer-Projector/dp/B08B64KM93

### Buzzer

![51zOdI55ndL _AC_SX679_](https://user-images.githubusercontent.com/113784775/209007383-f58d7216-e6b0-4916-b0c4-995bc2143a08.jpg)

Amazon: https://www.amazon.com/Cylewet-Electronic-Magnetic-Continuous-Arduino/dp/B01N7NHSY6

### QT Py RP2040

![adafruit_qtpy_rp2040](https://user-images.githubusercontent.com/113784775/209007910-0feade88-cdfe-4d80-8020-d9d7c0c42eed.jpg)

Adafruit: https://www.adafruit.com/product/4900

### APDS 9960

![3595-03](https://user-images.githubusercontent.com/113784775/209008146-7e1b2b2c-2621-46ea-a47b-6b4efc9e97e6.jpg)

Adafruit: https://www.adafruit.com/product/3595

## Assembly

### Overview

![9468d6a5488b16e94c7766e25f1e825](https://user-images.githubusercontent.com/113784775/209008305-e5cfc9e0-2864-444b-94f8-6f5eeb9a1588.jpg)

Pico4ml is controlled by the A3 pin of QT Py RP2040. Remember that all devices need to connect to ground.

### VGA Connection

![image](https://user-images.githubusercontent.com/113784775/209008429-0c7eedca-1f97-473b-bcb6-910f6b9d54e3.png)

![微信图片_20221221165025](https://user-images.githubusercontent.com/113784775/209008699-a0992c8d-1428-441f-8dc7-fb4a902d96fd.jpg)

Both of HSYNC and VSYNC are connected from the GPIO ports (17 and 21) of the RP2040 to the appropriate pins on the VGA connector. The display expects a voltage in the range of 0-0.7V. The output from the RP2040 is 3.3V. So, putting resistors between the R/G/B color pins (18, 19, and 20) and the VGA connector creates a voltage divider that keeps the output voltage within a safe range for the display.

### Bluetooth Connection

![image](https://user-images.githubusercontent.com/113784775/209009473-d8b71b0e-6a13-461b-84e7-e6d08e76d7d4.png)

![微信图片_20221221165834](https://user-images.githubusercontent.com/113784775/209010072-11a015bd-9995-4d9b-a1bb-20cd1bb28fd5.jpg)

HC-05 bluetooth uses the 2.45GHz frequency band. The transfer rate of the data can vary up to 1Mbps and is in range of 10 meters. The HC-05 module can be operated within 4-6V of power supply. It supports baud rate of 9600, 19200, 38400, 57600, etc. TXD of HC-05 connects to the A0 pin of QT Py RP2040, and RXD connects to the A1 pin.

### APDS 9960

APDS 9960 connects to QT Py RP2040 through STEMMA QT / Qwiic JST SH 4-pin Cable.

### Buzzer

Buzzer connects to the A3 pin of QT Py RP2040.

## Block Diagram

![屏幕截图 2022-12-21 171247](https://user-images.githubusercontent.com/113784775/209012161-063ebedd-2c7d-49bf-b55e-f523b14568d1.png)

RP2040 controls modules in the system. APDS9960 measures distance from the visitor. When the visitor is close to a certain distance, the buzzer alerts, and the camera in Pico4ML captures the image and sends to the screen. After checking the identification of the visitor, the user can change the status of the system (alarm on or off) through the Bluetooth.

## RP 2040 Set Up Environment

https://github.com/zgu74/Setup-Guide.git

## Project Code

# Project Development





