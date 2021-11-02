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

- insert image "Fig x: CT-Sail with metal housing, thermistor located beneath the salinity sensor. (Isabelle Giddy)" add arrows!

#### Pumped
The Glider Payload CTD (GPCTD) is a modular, self-contained CTD with memory and an integrated pump. 
The GPCTD improves on the CT-Sail through simpler installation requirements as well as a pump which allows for constant flow through the conductivity sensor. 
The CT sensors are ducted and pumped on the GPCTD with the intake positioned to minimize measurement errors caused by the vehicle’s thermally contaminated boundary flow (Janzen and Creed, 2011). 
Power consumption is 175 mW when continuously recording at 1 Hz. 

Seabird provided GPCTD accuracy ratings are: Conductivity: +- 0.0003 S/m over a range of 0 to 9 S/m; Temperature:  +- 0.002oC over a range of -5 - 42oC and Pressure:  ± 0.1% of full scale range, up to 2000 m (datasheet-GliderPayloadCTD-Aug15-2.pdf). 

- insert image "Figure xx: Slocum Glider CTD (pumped). The thermistor is located within the inflow valve on the left (Isabelle Giddy)" add arrows!

A variation of the GPCTD has been developed for installation on SLOCUM gliders. The sensor is installed on the side of the SLOCUM. The continuously pumped CTD consumes 240 mW sampling continuously at 1/2 Hz.

### RBRlegato3
The RBRlegato3 is an integrated CTD and logger package designed specifically for gliders with a hydrodynamic profile. 
It is available in slow (1 s) and fast (0.1 s) response temperature options as well as normal (2 Hz) and fast (16 Hz) sampling speeds. 
The RBRlegato3, unlike the previously mentioned sensors, has an inductive cell rather than conductive, with significant implications for sensor calibration of salinity. 
Its advantages are a large unpumped flow cell, reducing occurrence of spikes due to bubbles and fouling. 
As such, it is very good for near-surface applications and slow glider speeds, as well as for glider missions involving instrumentation sensitive to vibration (e.g., shear probes) or noise (e.g., acoustic packages). 
The Legato has low power consumption (45 mW) when sampling at 2 Hz. Its profile and low power have many benefits, but the inductive cell and relative youth of the sensor leave some open questions regarding long term accuracy.
As a logger, the RBRlegato3 can also integrate other RBR sensors (such as the oxygen Coda optode) enabling fast 16 Hz sampling even if the glider platform does not have the capability onboard and reduces the number of sensor ports required to connect to the glider. 
The RBRlegato3 has a manufacturer-provided accuracy of ± 0.002°C (ITS-90) over a range of -5 to +35°C (https://rbr-global.com/products/oem/rbrlegato). 

## Sensor integratons with gliders

### Mounting location

#### Spray
- expert missing

