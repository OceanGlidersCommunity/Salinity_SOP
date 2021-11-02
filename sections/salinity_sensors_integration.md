# Sensors and integrations

## CTD Sensors
On gliders, currently three types of CTD-sensors are in use (see Table 1). 
CT sensors can be unpumped (sections 2.1.1; 2.2) or pumped (section 2.1.2). 
Unpumped CT sensors have lower power consumption requirements as well as reduced susceptibility to blockages/failures because of the larger throughflow pipe (section 6.3.4). 
There is also reduced background vibration and noise, which is advantageous when measuring microstructure (reference to microstructure SOP in future). 
However, the disadvantage of the unpumped sensors is in the post processing correction for the effects of thermal-inertia because the flow rate through the inlet is not known and has to be estimated from the glider’s flight model (section 7). 
Pumped CT sensors on the other hand, have a constant through-flow rate, allowing for a simpler correction of thermal-inertia. Nevertheless, both pumped and unpumped sensors require corrections for thermal-inertia (section 7). 

### Seabird
Conductivity, temperature and depth (CTD) sensors distributed by sea-bird electronics is currently the most widely used sensor on gliders. 

#### Unpumped
The CT-Sail is a free-flushed (unpumped) CTD (SBE41) and was the first science payload installed in the Seaglider (Janzen and Creed, 2011) and remains widely in use. 
The separate temperature and conductivity are installed on the upper side of the glider pressure hull and integrated with the internal glider data acquisition and flight control system. 
On the CT sail the temperature sensor is positioned beneath and parallel to the conductivity sensor. 
The conductivity sensor itself is positioned within a metal housing with hole cut-outs to allow for flushing. The pressure sensor is located ~40 cm in front of the thermistor, requiring a slight spatial alignment with the sensors. 
Power consumption is 21 mW while profiling. 
The sampling speed is set by the user, typically to 2 Hz.  

Seabird provided CTD SBE41-sensor accuracy ratings: Conductivity: +- 0.0003 S/m over a range of 0 to 7 S/m; Temperature:  +- 0.002oC over a range of -5 - 45oC and Pressure:  +- 2 dbar over a range of 0-2000 m (datasheet_sbe41-1.pdf).

- insert image "Fig x: CT-Sail with metal housing, thermistor located beneath the salinity sensor. (Isabelle Giddy)"

