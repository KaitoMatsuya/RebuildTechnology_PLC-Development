# Abnormality-Detection-Patlite-System

About SLMP Ethernet Protocol(3E Frame)↓
1. https://qiita.com/BerandaMegane/items/b9cee359e8da90d4ce8e
2. https://qiita.com/hidehito108/items/e8eca75a46ee7d59feed
3. https://qiita.com/inari1047/items/f01f632989d5f5c51a11

Planned communication specifications↓

Upon detecting an abnormality: Send 0x01 to PLC register D1 (rotating signal light activates).

Upon returning to normal: Send 0x02 to PLC register D2 (rotating signal light stops).


Transmission Data Format Specifications↓

Common Section (Sub-header to Sub-command)

Sub-header: 0x50, 0x00, 
Network No: 0x00, 
Destination Station No: 0xFF, 
I/O No: 0xFF, 0x03, 
Destination Multidrop
Station No: 0x00, 
Data Length: 0x0C, 0x00, 
Watchdog Timer: 0x00, 0x00, 
Command: 0x01, 0x14, 
Sub-command: 0x00, 0x00

Variable Section (Start Device to Main Data)

When an abnormality is detected

Start Device: 0x01, 0x00, 0x00(Corresponds to PLC register D1.), 
Device Code: 0xA8, 
Number of Devices: 0x01, 0x00, 
Main Data: 0x01, 0x00, 

Upon recovery to normal status

Start Device: 0x02, 0x00, 0x00(Corresponds to PLC register D2.), 
Device Code: 0xA8, 
Number of Devices: 0x01, 0x00, 
Main Data: 0x02, 0x00

