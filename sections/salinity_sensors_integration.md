(sensors-integration)=
# Sensors and integrations

(ctd-sensors)=
## CTD Sensors
On gliders, currently three types of CTD-sensors are in use (see [Table 1](table1)). 
CT sensors can be unpumped ([Sections 3.1.1.1](unpumped); [3.1.2](rbr-legato)) or pumped ([Section 3.1.1.2](pumped)). 
Unpumped CT sensors have lower power consumption requirements as well as reduced susceptibility to blockages/failures because of the larger throughflow pipe ([Section 6.2.4](pump-malfunction)). 
There is also reduced background vibration and noise, which is advantageous when measuring microstructure {cite}`fer_microstructure_2014`. 
However, the disadvantage of the unpumped sensors is in the post processing correction for the effects of thermal-inertia because the flow rate through the inlet is not known and has to be estimated from the glider’s flight model ([Section 8.1](dynamic-error-correction)). 
Pumped CT sensors on the other hand, have a constant through-flow rate, allowing for a simpler correction of thermal-inertia. Nevertheless, both pumped and unpumped sensors require corrections for thermal-inertia ([Section 8.1](dynamic-error-correction)). 

(sea-bird)=
### Sea-Bird
Conductivity, temperature and depth (CTD) sensors distributed by Sea-Bird electronics is currently the most widely used sensor on gliders. 

(unpumped)=
#### Unpumped
The CT-Sail, a free-flushed (unpumped) CTD (SBE41), was the first science payload installed in the Seaglider {cite}`janzen_physical_2011` and remains widely in use. 
The separate temperature and conductivity sensors are installed on the upper side of the glider pressure hull and integrated with the internal glider data acquisition and flight control system. 
On the CT-Sail the temperature sensor is positioned beneath and parallel to the conductivity sensor. 
The conductivity sensor itself is positioned within a metal housing with hole cut-outs to allow for flushing. The pressure sensor is located ~40 cm in front of the thermistor, requiring a slight spatial alignment with the sensors. 
Power consumption is 21 mW while profiling. 

Sea-Bird provided [CTD SBE41-sensor](https://www.seabird.com/sbe-41-argo-ctd/product?id=54627907875) accuracy ratings: Conductivity: ± 0.0003 S m<sup>-1</sup> over a range of 0 to 7 S m<sup>-1</sup>; Temperature:  ± 0.002<sup>o</sup>C over a range of -5 - 45<sup>o</sup>C and Pressure: ± 2 dbar over a range of 0-2000 m.

:::{figure-md} CT-SAIL
<img src="/images/giddy_CT_sail.png" alt="CT-SAIL" class="bg-primary mb-1" width="400px">

CT-Sail with metal housing, thermistor located beneath the salinity sensor. (Figure credit: Isabelle Giddy)
:::

(pumped)=
#### Pumped
The [Glider Payload CTD (GPCTD)](https://www.seabird.com/glider-payload-ctd-gpctd/product?id=60762467712) is a modular, self-contained CTD with memory and an integrated pump. 
The GPCTD improves on the CT-Sail through simpler installation requirements as well as a pump which allows for constant flow through the conductivity sensor. 
The CT sensors are ducted and pumped on the GPCTD with the intake positioned to minimize measurement errors caused by the vehicle’s thermally contaminated boundary flow {cite}`janzen_physical_2011`. 
Power consumption is 175 mW when continuously recording at 1 Hz.

Sea-Bird provided GPCTD accuracy ratings are: Conductivity: ± 0.0003 S m<sup>-1</sup> over a range of 0 to 9 S m<sup>-1</sup>; Temperature:  ± 0.002<sup>o</sup>C over a range of -5 - 42<sup>o</sup>C and Pressure: ± 0.1% of full scale range, up to 2000 m. 

:::{figure-md} SLOCUM-CTD
<img src="/images/giddy_slocum_CTD.png" alt="SLOCUM-CTD" class="bg-primary mb-1" width="400px">

Slocum Glider CTD (pumped). The thermistor is located within the inflow valve on the left (Image credit: Isabelle Giddy)
:::

A variation of the GPCTD, the [Slocum Glider CTD](https://www.seabird.com/slocum-glider-ctd/product?id=60762467713&callback=qs) has been developed for installation on SLOCUM gliders. The sensor is installed on the side of the SLOCUM. The continuously pumped CTD consumes 240 mW sampling continuously at 0.5 Hz.

(rbr-legato)=
### RBR*legato*<sup>3</sup>
The [RBR*legato*<sup>3</sup>](https://rbr-global.com/products/oem/rbrlegato) is an integrated CTD and logger package designed specifically for gliders with a hydrodynamic profile. 
It is available in slow (1 s) and fast (0.1 s) response temperature options as well as normal (2 Hz) and fast (16 Hz) sampling speeds. 
The RBR*legato*<sup>3</sup>, unlike the previously mentioned sensors, has an inductive cell rather than conductive, with significant implications for sensor calibration of salinity. 
Its advantages are a large unpumped flow cell, reducing occurrence of spikes due to bubbles and fouling. 
As such, it is very good for near-surface applications and slow glider speeds, as well as for glider missions involving instrumentation sensitive to vibration (e.g., shear probes) or noise (e.g., acoustic packages). 
The Legato has low power consumption (45 mW) when sampling at 2 Hz. Its profile and low power have many benefits, but the inductive cell and relative youth of the sensor leave some open questions regarding long term accuracy.
As a logger, the RBR*legato*<sup>3</sup> can also integrate other RBR sensors (such as the oxygen Coda optode) enabling fast 16 Hz sampling even if the glider platform does not have the capability onboard and reduces the number of sensor ports required to connect to the glider. 

The RBR*legato*<sup>3</sup> has a manufacturer-provided accuracy of ± 0.002<sup>o</sup>C (ITS-90) over a range of -5 to +35<sup>o</sup>C. 

(integration)=
## Sensor integrations with gliders

(mounting-location)=
### Mounting location

(spray)=
#### Spray
- expert missing

(seaglider)=
#### Seaglider
On Seagliders the Sea-Bird electronics supplied CT-Sail is mounted on the upper side of the glider pressure hull. 
Flow past the CT sensors relies solely on the movement of the glider. 
Sea-Bird no longer lists the CT-Sail but is manufactured on request by integrators. 
The Glider Payload CTD replaces the CT-Sail and was developed for easier integration and improved data output associated with the addition of a pump to control flow past the sensors. 
The GPCTD is installed between the pressure hull and the fairing in the aft-flooded payload bay. 

:::{figure-md} SEAGLIDER_CTSAIL
<img src="/images/giddy_seaglider_CTSail.png" alt="SEAGLIDER_CTSAIL" class="bg-primary mb-1" width="400px">

Unpumped CT-Sail mounted above the pressure hull on a Seaglider. (Image credit: Isabelle Giddy)
:::

(slocum)=
#### Slocum
On slocum gliders, an adaptation of the GPCTD, the Slocum Glider CTD, is installed beneath a wing on the lateral side of the glider. 

:::{figure-md} SLOCUM-CTD_INSTALLED
<img src="/images/giddy_slocum_glider_CTD.png" alt="SLOCUM-CTD-INSTALLED" class="bg-primary mb-1" width="400px">

Slocum Glider CTD installed on a Slocum G2 beneath the wing.  (Image credit: Isabelle Giddy)
:::

(seaexplorer)=
#### SeaExplorer
On SeaExplorer gliders, the CTDs are typically installed in the flooded nose cone area ({numref}`RBR_LEGATO_SEAEXPLORER`, left), though the RBR*legato*<sup>3</sup> can also be configured to be installed through one of the top/side “puck” ports to leave the nose available for other sensors (e.g. acoustic payloads) as shown in {numref}`RBR_LEGATO_SEAEXPLORER`, right. 

:::{figure-md} RBR_LEGATO_SEAEXPLORER
<img src="/images/queste_clark_rbr_legato.png" alt="RBR_LEGATO_SEAEXPLORER" class="bg-primary mb-1" width="400px">

RBR*legato*<sup>3</sup> CTD on SeaExplorer (Image credits: Bastien Queste (left) and Clark Richards (right))
:::

In the case of the Sea-Bird GPCTD, the sensors are integrated on the wet payload part located on the front nose of the SeaExplorer glider, with the integrated pump providing a constant flow through the conductivity cell.

:::{figure-md} GPCTD
<img src="/images/evi_GPCTD.png" alt="GPCTD" class="bg-primary mb-1" width="400px">

Left: Sea-Bird GPCTD on SeaExplorer; Right:  GPCTD on SeaExplorer during in lab preparation (Image credit: Evi Bourma)
:::

(petrel)=
#### Petrel Glider
The small-size RBR*legato*<sup>3</sup> CTD is embedded in the front fairing of the Petrel glider. 
The CT sensors are exposed outside the fairing to sense the ambient seawater. 
This integration design can minimize the impact of the CTD on the streamline of gliders. 

:::{figure-md} RBR_PETREL
<img src="/images/wang_rbrlegato3.png" alt="RBR_PETREL" class="bg-primary mb-1" width="200px">

RBR*legato*<sup>3</sup> Petrel Glider integrated an RBR<i>legato</i><sup>3</sup> CTD in the front fairing. (Image credit: Joe Wang)
:::

(sensor-sampling)=
### Sensor sampling rates
While each sensor has a range of sampling rates that can be set, the real limitation is set by the processing system associated with the platform.

Sensors integrated on [Seagliders](seagliders) are limited to once every 5 seconds (0.2 Hz), unless the seaglider is installed with a scicon board (discontinued). 

[SeaExplorers](seaexplorer) have a dedicated ARM processor and can handle up to 16Hz. 

Older [Slocums](slocum) with a persistor typically sample once every 4 seconds (0.25 Hz). This can be changed to once every 2 seconds (0.5 Hz) when the science persistor has 'free' time, meaning when you do not have too many other sensors.
Recent models (eg. G3) can handle faster sampling rates.  

(sensor-storage)=
### Sensor storage
Sensors are stored dry with sensor caps on or tape to cover open valves, and protected from dust and freeze. 
