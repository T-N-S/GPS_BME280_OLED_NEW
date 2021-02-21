# GPS_BME280_OLED_NEW
GPS Data Logger build from scratch to replace Box_GPS_BME280_OLED

* Due to hardware issues and bad PCB design, this sketch will replace
  the old Box_GPS_BME280_OLED firmware
* OLED output can be switched of by commenting the DEBUG flag on top of the sketch
* Data can be stored on SD with ENLOG enabled. Format: CSV
  ```
  date       time     lat       lng       alt   temp hum   pres
  2021-02-20;18:14:14;51.613304;14.498220;69.00;7.82;68.11;1012.45;
  2021-02-20;18:14:18;51.613304;14.498228;68.80;7.82;67.90;1012.45;
  2021-02-20;18:14:22;51.613300;14.498223;68.40;7.81;68.23;1012.39;
  2021-02-20;18:14:25;51.613304;14.498223;68.40;7.81;68.15;1012.39;
  2021-02-20;18:14:29;51.613304;14.498218;68.30;7.75;67.88;1012.36;
  2021-02-20;18:14:32;51.613300;14.498235;68.40;7.79;67.86;1012.42;
  2021-02-20;18:14:36;51.613297;14.498217;68.50;7.80;68.26;1012.45;
  2021-02-20;18:14:39;51.613304;14.498230;68.80;7.79;68.14;1012.42;
  2021-02-20;18:14:43;51.613312;14.498222;68.90;7.77;68.29;1012.44;
  2021-02-20;18:14:46;51.613293;14.498212;69.20;7.77;68.51;1012.44;
  2021-02-20;18:14:50;51.613297;14.498219;69.60;7.75;68.55;1012.41;
  2021-02-20;18:14:54;51.613289;14.498223;70.40;7.71;68.80;1012.36;
  2021-02-20;18:14:57;51.613285;14.498228;71.00;7.77;69.24;1012.39;
  2021-02-20;18:15:01;51.613274;14.498179;71.40;7.79;68.97;1012.34;
  2021-02-20;18:15:04;51.613243;14.498161;71.60;7.82;69.27;1012.42;  
  ```
  * Wiring to Arduino:
    I2C devices, for both BME280 and OLED
    * SDA - A4 - level shifter 5V <-> 3V3
    * SCL - A5 - level shifter 5V <-> 3V3

    ![](https://github.com/NaWiSchool/GPS_BME280_OLED_NEW/blob/main/Images/IMG_20210220_171854512_HDR.jpg)
    ![](https://github.com/NaWiSchool/GPS_BME280_OLED_NEW/blob/main/Fritzing/GPS_BME280_OLED_NEW_Fritzing_Steckplatine.png)
    
  * SPI - CardReader
    * MOSI - pin 11
    * MISO - pin 12
  * CLK - pin 13
    * CS - pin 10
  
  * Serial - GPS
    * TX - D3, connects to RX of GPS (can be skipped, no data send from Arduino to GPS)
    * RX - D4, connects to TX of GPS

## TODOs

  * Flush Lat: and Lng: values to the left on OLED

## Issues

  * Short of memory, might affect stability -> disable OLED


