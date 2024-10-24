# iobroker
Power Management with Sungrow PV Inverter, Hoval Heat Pump &amp; Shelly Meter &amp; Switches

## Sungrow Inverter
  - Model: Sungrow SH20T
  - MTTP: 3

### Sungrow Modbus Integration
Since WiNet-S / WiNet-S2 does not provide reliable data until now we use the external RS485 connection.

#### Model
[Waveshare RS485 to POE](https://www.waveshare.com/wiki/RS485_TO_POE_ETH_(B))

#### Connection
SH20T "Logger" port on COM2 
<img width="1208" alt="grafik" src="https://github.com/user-attachments/assets/a3275689-7bc0-4a29-ab8a-a4c30358c76c">

#### Settings
Work Mode: TCP Server
<img width="1357" alt="grafik" src="https://github.com/user-attachments/assets/5a113eed-8e48-4cf9-80c4-de447bd077b7">

### Modbus Registers
todo

## Hoval Heat Pump
  - Model: Ultrascource B
  - Buffer: 300 lt

### Hoval CANbus Integration
The Hoval Modbus gateway seemed to be too expensive, so we decided to go for a CANbus gateway.

#### Model
[Hoval CAN-Gateway](https://github.com/wladwnt/CAN-Gateway)

#### CANbus parameters
```
param=0;1;0;0;0;r;AF1_Aussenfuehler_1_gradC;10;S16;0.100000;0.000000;
param=0;1;2;0;4;r;Warmwasser_Ist_SF_gradC;10;S16;0.100000;0.000000;
param=0;1;2;0;2052;r;Status_Warmwasserregelung;10;U8;1.000000;0.000000;
param=0;1;2;0;1004;r;Warmwasser_Soll_gradC;10;S16;0.100000;0.000000;
param=0;1;3;0;1096;r;Anlagetemp_Soll_Heizen_aktuell_gradC;10;S16;0.100000;0.000000;
param=0;1;3;0;1097;r;Anlagetemp_Soll_WW_aktuell_gradC;10;S8;1.000000;0.000000;
param=0;1;3;0;2054;r;Status_Warmemanager;10;U8;1.000000;0.000000;
param=0;1;3;0;1015;w;Puffertemperatur_oben_Sollwert_gradC;10;S16;0.100000;0.000000;
param=0;1;10;1;9020;w;Solltemperatur_Handbetrieb_gradC;10;S16;0.100000;0.000000;
param=0;1;10;1;9075;w;Betriebswahl_Waermeerzeuger;10;U8;1.000000;0.000000;
param=0;1;10;1;9037;w;Temperatur_Ueberhoehung_Abschlag_WEZ_K;10;S16;0.100000;0.000000;
param=0;1;60;7;1570;r;WPF_Waermepumpenpufferfuehler_gradC;10;S32;0.100000;0.000000;
param=0;1;0;0;38012;w;Smart_Grid_ueber_Systembus;10;U8;1.000000;0.000000;
param=0;1;0;0;38013;w;Ausloeser_Smart_Grid_Funktion;10;U8;1.000000;0.000000;
param=0;1;0;0;21090;r;Status_Smart_Grid;10;U8;1.000000;0.000000;
param=0;1;0;0;38003;w;SG_Mindestleistung_kW;10;U16;0.010000;0.000000;
param=0;1;2;0;5077;w;Smart_Grid_Offset_WW_Sollwert_K;10;S16;0.100000;0.000000;
param=0;1;1;0;7031;w;SmartGrid_Offset_Raum_Sollw_Heizen_K;10;S16;0.100000;0.000000;
param=0;1;0;0;30052;w;Zuo._Eing._SmartGrid_1;10;U8;1.000000;0.000000;
param=0;1;0;0;30053;w;Zuo._Eing._SmartGrid_2;10;U8;1.000000;0.000000;
param=0;1;0;0;30054;w;Zuo._Eing._Sollwert_Erhohung;10;U8;1.000000;0.000000;
param=0;1;0;0;30055;w;Zuo._Eing._Sollwert_Reduktion;10;U8;1.000000;0.000000;
param=0;1;1;0;7031;w;SmartGrid_Offset_Raum_Sollw_Heizen_K;10;S16;0.100000;0.000000;
param=0;1;1;0;7046;w;SmartGrid_Offset_Raum_Sollw_Kuehlen_K;10;S16;0.100000;0.000000;
param=0;1;1;1;7031;w;SmartGrid_Offset_Raum_Sollw_Heizen_K;10;S16;0.100000;0.000000;
param=0;1;1;1;7046;w;SmartGrid_Offset_Raum_Sollw_Kuehlen_K;10;S16;0.100000;0.000000;
param=0;1;2;0;5077;w;Smart_Grid_Offset_WW_Sollwert_K;10;S16;0.100000;0.000000;
param=0;1;10;1;20052;r;Modulation_percent;10;U8;1.000000;0.000000;
param=0;1;10;1;23002;r;Aktuelle_elektr_Leistungsaufnahme_WEZ_kW;10;S16;0.010000;0.000000;
param=0;1;1;0;3050;w;Betriebswahl_Heizung;10;U8;1.000000;0.000000;
param=0;1;1;0;1;w;Raum_Ist_gradC;10;S16;0.100000;0.000000;
param=0;1;1;0;2;r;Vorlauf_Ist_gradC;10;S16;0.100000;0.000000;
param=0;1;1;0;1001;r;Raum_Soll_gradC;10;S16;0.100000;0.000000;
param=0;1;1;0;1002;r;Vorlauf_Soll_gradC;10;S16;0.100000;0.000000;
param=0;1;1;0;1020;r;Pumpe;10;U8;1.000000;0.000000;
param=0;1;1;0;1021;r;Mischer_percent;10;S8;1.000000;0.000000;
param=0;1;1;0;2051;r;Status_Heizkreisregelung;10;U8;1.000000;0.000000;
```

