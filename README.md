# Nixies_Board
This repository stores Nixie Clock board and schematics created in Eagle.

The design goal is to create a Nixie clocks driven by low-cost ARM processor with simple serial interface which is used for clock power down scenario remedy and for time synchronization. The actual solution for the time synchronization is up to the user and can be realized by e.g. Bluetooth or Wifi modules like Wemos D1.

Notes:
 - Power supply is based on https://threeneurons.wordpress.com/nixie-power-supply/
 - I saw that a lot of people had an issue with ghosting when multiplexing the nixies. I was not an exception. The solution is to connect all cathodes to pre-bias voltage of 100V via e.g. 220K rezistors (check the schematics for more details).  Refer to Section "OFF CATHODE CHARACTERISTICS" at http://www.zapro.dk/public/PDF/nixie/N101.pdf to find magic behind.
