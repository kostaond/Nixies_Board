# Nixies_Board
This repository stores Nixie Clock PCB board and schematics created in Eagle. It also contains drawings and 3D model of the metal box. 

The design goal is to create a Nixie clocks driven by low-cost ARM processor with simple serial interface which is used for clock power down scenario remedy and for time synchronization. The actual solution for the time synchronization is up to the user and can be realized by e.g. Bluetooth or Wifi modules like Wemos D1.

![Image of Clock](https://github.com/panzer412/Nixies_Board/blob/master/photos/IMG_7219_1.jpg)

Notes:
 - Power supply is based on https://threeneurons.wordpress.com/nixie-power-supply/
 - High voltage part of the design can be disabled by disconnecting JP2. This is handy for software debugging from the safety perspective.
 - I saw that a lot of people had an issue with ghosting when multiplexing the nixies. I was not an exception. The solution is to connect all cathodes to pre-bias voltage of 100V via e.g. 220K rezistors (check the schematics for more details).  Refer to Section "OFF CATHODE CHARACTERISTICS" at http://www.zapro.dk/public/PDF/nixie/N101.pdf to find magic behind.

Two revisions exist in this repository – REV1 and REV2 (see tags). 
* The REV1 is the very first prototype where the wrong BCD decoder was used (74HC42 with active low output while BCD decoder with active high should have been used). This could be partially resolved by resoldering with 4028, external wiring and SW workaround. However DO NOT use this version!
* The REV2 fixes the issue with the BCD decoder, resolves ghosting and adds footprint preparation for Wemos D1 Wifi modul.
