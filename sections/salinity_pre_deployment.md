# Pre-deployment operations and calibrations

## Storage and cleaning
Optode foils typically drift more while in storage than while in use, the reasons for this are thought to be due to exposure to UV radiation and dry air {cite}`Bittig2018`, {cite}`Aanderaa2018`. 
We recommend that all optodes should be stored away from the light (especially fluorescent lights), keep the foil humid and use the plastic caps provided with the sensor. Two-point calibration prior to deployment is always recommended.
Sensors should be cleaned before storage and stored with black caps on, including some Milli-Q or tap water, or with a piece of wet cotton taped against the foil. 
If sensors are stored dry the foil will dry out which could lead to 1-2 % lower readings. 
The sensor then needs to be placed in water to hydrate at least 24 h prior to starting field measurements again.

<!-- 
![Keeping sensor in small beakers before and during calibration process. Only the membrane will need to be submerged in distilled water. \label{fig:storage}](/images/storage.jpg)
-->

:::{figure-md} storage
<img src="/images/storage.jpg" alt="Sensor storage" class="bg-primary mb-1" width="400px">

Keeping sensor in small beakers before and during calibration process. Only the membrane will need to be submerged in distilled water.
:::

After recovery the sensor has to be cleaned to remove any biofouling. The following protocol is recommended by the manufacturer: 
1. If the sensor has been for too long exposed to the air, leave it overnight in a vinegar solution.
2. Next day, place the sensor in soapy water and use a brush gently if it is necessary to remove all material adhered to the surface.
3. Rinse very well with clean water and dry carefully. 

*NOTE: Don’t change the foil unless it is physically damaged.* 

## Sensor configuration for deployment
Salinity configuration: 0 PSU. For optode sensors: when there is a small variation in salinity (less than 1 g/kg), it can be set to the mid value avoiding the need of salinity compensation. However, even in that case, it is a good practice to set salinity to 0 for two reasons: 1) it is usually difficult to find the salinity value defined for old deployments and 2) in case the equations change, it would be easier to recalculate oxygen values from uncompensated values. 

## Sensor integration with gliders
Optodes should be configured to record the intermediate parameters (`calphase` and temperature), not just oxygen concentration or saturation.
Accurate time-stamps, or offsets relative to CT measurements must be recorded for performing the lag correction.

### Mounting location

#### Spray
- input from expert needed

#### Seaglider
On Seagliders the oxygen sensor is normally mounted externally behind the CT sensor (see {numref}`seagliders_standard`. Given this exposed location it is important to mount the optode with the sensing foil facing away from incident light to avoid unnecessary UV exposure.
<!-- 
![UEA OGIVE seaglider with 4330F optode, together with NOC LoC spectrophotometric pH, unpumped SBE CT and Fluidion potentiometric pH sensor. \label{fig:seagliders_standard}](/images/OGIVE.png)
-->

:::{figure-md} seagliders_standard
<img src="/images/OGIVE.png" alt="Seaglider sensor integration" class="bg-primary mb-1" width="400px">

UEA OGIVE seaglider with 4330F optode, together with NOC LoC spectrophotometric pH, unpumped SBE CT and Fluidion potentiometric pH sensor.
:::


#### Slocum
On slocum gliders the oxygen optode is typically installed aft close to the fin ({numref}`slocum_standard`.

<!--
![Standard Aanderaa optode 4831 mounting under the fin of the Slocum G2. \label{fig:slocum_standard}](/images/slocum.jpg)
-->

:::{figure-md} slocum_standard
<img src="/images/slocum.jpg" alt="Slocum sensor integration" class="bg-primary mb-1" width="400px">

Standard Aanderaa optode 4831 mounting under the fin of the Slocum G2.
:::

However this positioning is not ideal for oxygen measurements due to the optode being within a region of laminar flow {cite}`Moat2016`, additionally the optode response time has been observed to be dependent on the sensor orientation relative to the direction of flow {cite}`Bittig2014`. 


An alternative mounting of the Aanderaa optode in a more prominent location fore of the glider fin has been demonstrated as being much more suitable for measuring oxygen on gliders ({numref}`slocum_alternative_mounting`) {cite}`NicholsonFeen2017`. 
This mounting location means that the sensor foil faces the flow directly and therefore the diffusive boundary layer thickness at the optode membrane is minimised, reducing the optode response time. 
Furthermore, this mounting location also means that in-situ in-air calibrations can be performed during deployment (similar to those done with Argo floats) which are beneficial when processing the DM oxygen data (see ‘in-air calibration’ section).

<!--
![Slocum glider showing alternative mounting of an Aanderaa optode perpendicular to the fin. \label{fig:slocum_alternative_mounting}](/images/slocum_better_location.jpg)
-->

:::{figure-md} slocum_alternative_mounting
<img src="/images/slocum_better_location.jpg" alt="Slocum better O2 sensor location" class="bg-primary mb-1" width="400px">

Slocum glider showing alternative mounting of an Aanderaa optode perpendicular to the fin.
:::

#### SeaExplorer
On SeaExplorer gliders, all existing oxygen sensor integrations are installed in the forward wet payload section (the nose cone). External mounting is also feasible using external puck mounts on the dry payload, located approximately 1/3 of the way back, but is rare and generally only used for instrument trials. The Rinko AROD-FT is generally installed on the forward starboard connector, with the sensing foil and temperature probe 15 centimeters back from the tip of the nose and lightly sheltered to avoid damage when making contact with the nose. Both the foil and temperature probe are well exposed to flow. The new RBR Coda integration is also planned to present the foil and probe slightly set back from the tip of the nose, while remaining exposed to unmodified flow. The SBE43 is found only when accompanied with a Seabird pumped CT sensor; both of these sensors are placed in the nose where the RBR Legato CT sensor can be seen in {numref}`Rinko`.

<!--
![Rinko AROD-FT in the flooded nose cone payload bay of a SeaExplorer next to an RBR Legato sensor.](/images/Rinko.png)
-->

:::{figure-md} Rinko
<img src="/images/Rinko.png" alt="Rinko" class="bg-primary mb-1" width="400px">

Rinko AROD-FT in the flooded nose cone payload bay of a SeaExplorer next to an RBR Legato sensor.
:::


### Antifouling
Materials immersed in water experience a series of biological and chemical processes, resulting in the formation of complex layers with attached organisms. This biofouling can be divided into microfouling and macrofouling {cite}`Delgado2021`. 

In optodes sensors, biofouling can be severe enough to block oxygen molecules from entering the sensing foil. Aanderaa has different solutions that have been successfully applied, some includes: 

1) Copper tape (e.g. 3M 1181) or Copper/Nickel (last much longer) are easy antifouling solutions. 
When applying the tape, be sure that it is not in contact with any other metal parts otherwise, the tape will lose its antifouling properties.

2) Paints / coatings - optical sensors, so these can only reduce growth nearby but not on the actual sensing foil.

4) Ongoing trials: Aanderaa is focusing on non-toxic methods like fiber/hair cloth and “shark skin” film.

Mechanical wipers or UV radiation based approaches are generally unsuitable for gliders due to their increased power requirements and drag.

Regardless of whether efforts to prevent fouling are made, it is vital that post-recovery photographs are taken of the optode so that the impact of biofouling can be assessed during DMQC.

### Air saturation quality check
Based on in-air calibrations on Argo floats and gliders {cite}`BittigKoertzinger2015`, {cite}`Johnson2015`, {cite}`Bittig2015`, {cite}`NicholsonFeen2017` and {cite}`Bittig2018` a simpler method has been recommended by the manufacturer to do it before and after deployments (Aanderaa Best Practices for Maintaining High Data Quality). 
This could be used during campaigns. 
This won’t be useful if sensor foil is not wet or the temperature of the foil is different from that measured with the temperature sensor. 
You will need to leave the sensor logging outside in the free air for several hours before and after deployment. Remember to record the local air pressure. 

*NOTE: At sea level at standard air pressure (101.3 kPa = 1 Atm = 14.69 psi) the sensors should show 100 % if wet and 102 % if completely dry; at air pressure 100 kPa it should show (1.3/101.3)100 = 1.3 % lower. See also {numref}`air-pressure-effects`.*

*NOTE: It is highly recommended to do this protocol at night when humidity is higher and the temperature is lower and more stable.* 

## Pre-deployment calibration
Optodes and similar instruments generally drift more while in storage than in use. It is therefore essential that these instruments are recalibrated prior to glider deployment. This is necessary even if in-situ reference (Winkler) samples are taken during the deployment as they will not cover the full range of oxygen concentrations during the period of the mission. As the instrument drift manifests as an increasing offset from zero in addition to a reducing sensitivity, a two point calibration is required to rescale the optodes measuring range.

### Two point calibration procedure, optode example
This protocol is recommended to do for at least two different temperatures, which cover the expected in-situ temperature range. 
There are several possibilities in order to achieve this, some examples:
1. Doing the experiments in labs with different temperatures. You need to leave all materials, reagents and sensors in the lab/workshop/room at least 8 hours (e.g. overnight) before starting the calibration.
2. Doing the experiment in the lab and changing the temperature. This is possible if the lab has an AC that we can turn on/off or change the temperature in the lab. You need to leave all materials, reagents and sensors in the lab at least 8 hours (e.g. overnight) before starting the calibration.
3. Doing the experiment using a thermostatic bath. You need to leave the 0 and 100% solutions in the bath at least overnight before starting the calibration. It is most likely that you won’t be able to use a magnetic stirrer, so you need to be sure that you place the end of the bubble tube in the bottom of the bottle/beaker. 

In situ intercomparisons will be required to find the outset of the sensor in different seawater conditions. Therefore, samples should be taken in the tank during the ballasting (if this is 1-2 days before deployment, no more) and at the deployment/recovery site (ideally at different depths).

*NOTE: A multipoint DO calibration is necessary to obtain new foil coefficients and that can be done at the manufacturer laboratories or in any fully equipped calibration lab. These values shouldn’t be changed otherwise.*

The Winkler method is used to determine the concentration of dissolved oxygen in discrete water samples which is a highly accurate method for determination of dissolved oxygen (± 0.15 $\mu$mol/kg). We recommend to follow the GO-SHIP protocol described by {cite}`Langdon2010` and a well trained technician to do the sampling and analysis.

*NOTE: This procedure is suitable for the measurement of the full range of oceanic oxygen concentrations (0-400 $\mu$mol/kg) in uncontaminated seawater.*

:::{figure-md} 100-0-calibration
<img src="/images/100-0-calibration.png" alt="100 0 % calibration" class="bg-primary mb-1" width="400px">

Setup for 100% and 0% calibration.
:::

There are various issues with Winkler at low oxygen concentrations that have been described in the bibliography: 
 -	In waters with concentrations below 5 $\mu$mol/kg, high concentration of nitrite may cause a positive oxygen bias {cite}`Langdon2010`. In more recent articles, scientists even avoid using Winkler at concentrations below 20 $\mu$mol/kg {cite}`Thomsen2016`. 
 -	Oxygen absorbed in the plastic of the Niskin bottles is transferred into the water sampled. This oxygen contamination increases the concentration obtained when follow Winkler method. It has been measured values of apparent concentration of 2 - 4 $\mu$mol/kg in the Pacific minimum zones, showing a significant positive bias {cite}`Garcia-Robledo2021`.
 -	Presence of extremely low concentrations of oxygen concentrations (nmol levels) in areas like the core of the Peruvian oxygen minimum zones.

Thus, when working in these areas, it is recomended to do:
 - In-situ approaches for 0 % calibration suggested by {cite}`Thomsen2016`.
 - Intercomparisons with STOX sensors attached to a shipboard CTD {cite}`Revsbech2009` or new low-oxygen sensing foils (0-10% saturation) from Aanderaa.

#### 100 / 0 % saturation protocol

This method is necessary to check the sensor drift over time as the foil wears out. It’s recommended to do it before the deployment and after recovery. NOTE: Sensor foil must be wet during all procedure steps.   
Some information to read before we proceed with the calibration:
1. For a 100 % bubbled bath, connect an aquarium pump to a tube which has been fitted with a porous stone (bubble dispenser) at the end. This will create small air bubbles that are sufficient to equilibrate the water rapidly. 
NOTE: It is important that the aquarium pump takes in air from an open atmosphere outside, not from inside the room/laboratory where O2 levels will be affected by the on-going activities and/or the ventilation. To verify that optodes are in saturated water you can take them up from the water and hold them just above the surface for a few minutes. There should then be no change in the saturation readings (Aanderaa Best Practices).
2. For 0 % saturation solution, add 20 g sodium sulphite to approx. 1 L. Sodium sulphite rapidly removes the oxygen and, as long as crystals of the compound can be seen, the oxygen level in the water will stay at 0. Sodium sulphite also has the advantage of being inexpensive and the level of toxicity is low. This solution is considered irritating and wearing appropriate PPE (gloves, goggles and lab coat) is recommended.
There is also an option of removing the oxygen from the water bubbling nitrogen all time. In this case you have to be sure all oxygen is removed from the solution, this will happen after 3-5 minutes bubbling (maximum volume of 100 mL approx., for bigger volume you will have to increase the time). You have to keep injecting N2 during all time of the zero calibration.
3. If any residue of the  sodium sulphite solution remains on the sensing surface, the 100 % measurement will be inaccurate. Therefore, 100 % DO saturation calibration should be performed first. To avoid contamination, always rinse well with distilled water.
4. Immerse the sensor in the 100 % bath overnight. If this is not possible, having the sensor submerged in distilled water will be enough to keep the foil wet for the calibration.
5. Always check saturation values: an outset of ± 5 % is adequate, so a value between 95 to 105 % is correct.
6. While calibrating, measure air pressure and water temperature to calculate the DO saturation estimated at current pressure. When we are on board of a ship and would like to use the data from the ship weather station, we need to check where the calibration is taking place: lab air pressure will be influenced by air conditioning systems, location of the lab (at sea level or in decks below), size and occupancy of the lab,among others. These considerations should be taken into account when working in onshore labs also. Therefore,  having a portable weather station is highly recommended. For measuring temperature, a sonde with the same or better precision as the glider sensors must be used. 

#### Communicating with the sensor using a terminal program and a cable
When the DO sensor is disconnected from the glider:
1. Connect the sensor to a PC by using a Sensor Cable (Cable #3855 for 4330/4835 optodes, Cable #5335 for 4831).
2. Start a terminal program  with the following set-up:
9600 Baud
8 Data bits
1 Stop bit
No Parity
Xon/Xoff Flow Control
3. If using Tera Terminal Pro, after setting up the com port according to settings above please select “Terminal” in the “Set up” menu and click “Local echo” also select “CR+LF” for both “Receive” and “Transmit” under “New line”.
To stop, type ‘Do Stop’.
4. Once the sensor is measuring, continue with the procedure (see section Calibration Procedure).

There is also a possibility of using a Data Logger while we are working with the sensors. 

<!--
| image file missing |
|:--:|
| *Figure X: Recording data using a terminal program (left image) and using a data logger (right image).* |
-->

:::{figure-md} terminal_program
<img src="/images/TerminalProgram.jpg" alt="Terminal program" class="bg-primary mb-1" width="400px">

Recording data using a terminal program.
:::

#### Calibration procedure
Materials: Distilled water, aquarium pump, 1L and small volume beakers, stirrer and magnetic stirrer, BOD bottles, Winkler reagents, sodium sulfite solution, pipettes and tips, barometer, termometer.

Type *Get All* command for saving the initial sensor configuration to be able to restore old values in case something goes wrong.

1. With the sensor submerged in  the 100 % water, connect to it and start measuring.  Set the Interval property to 30 seconds. (This interval is recommended during the calibration to reduce the risk of self heating in the small container).
             
            Set Passkey(1000)
            
            Set Interval(30)
            
            Save
2. Wait until both the temperature and the phase measurements are stabilized.

3. Store calibration values by typing:
           
           Set Passkey(1000)
            
           Do CollectCalDataSat
The Save command is automatically performed.

4. Set the CalDataAPress property to the actual air pressure in hPa at the site:
           
           Set Passkey(1000)
           
           Set CalDataAPress (..)
          
           Save
5. Take 2 samples for Winkler measurement.

6. Dry the sensor carefully (make sure that the sensing foil is free from air bubbles) and immerse it in 0 % bath (0 % almost always reads correctly and is part of the calibration process). 
Wait until both the temperature and the phase measurements have stabilized (approx. 3 min).

7. To store calibration values for 0 %:
           
           Set Passkey(1000)
           
           Do CollectCalDataZero
The Save command is automatically performed.

8. To accept the new calibration and store the new coefficients in the sensor:
          
           Set Passkey(1000)
           
           Do Calibrate
The  Save command is automatically performed.

9. Rinse well with distilled water and dry the sensor foil carefully and check how it works at air. 
Save the data to check the sensor performance through time (a barometer is needed). 
Value of oxygen saturation should be 100 % or higher.

10. Put the sensor back into the 0 % water, the reading should drop to zero.

11. Set back the Interval property to 1 second (or the desired sampling frequency).
            
            Set Passkey(1000)
            
            Set Interval(1)
            
            Save
12. Type Get All command for saving the final sensor configuration for reference.

### In situ intercomparison in the tank during ballasting
This is an extra in situ intercomparison to carry out if  access to the tank while ballasting the glider is possible and the ballasting is close in time to the deployment (no more than 1-2 days before) (reference PLOCAN).

Materials: Silicon tube for sampling, multiparameter sonde, BOD bottles, Winkler reagents, pipettes and tips (or a bottle-top dispenser for reagent bottles), titration material (buretes or titrator).

1. The sensor should stay overnight submerged  in water to make the membrane wet. If the sensor is already mounted in the glider, use a wet sponge. 
*NOTE: Keep the sensor in the dark all time.*
4. Once the glider is in the ballasting tanks, place the silicon tube for sampling near the sensor.
5. Once the sensor measurements are stable (variations in the measurements are not higher than the precision/resolution of the sensor), start sampling water for Winkler analysis.  Take samples every 5-10 minutes, in total 4-6 samples will be required. *NOTE: Record the time we collect a sample for Winkler titration.*
6. A multiparameter sonde with a DO sensor whose precision is less than 0.1 % can be measured in the tank near the glider’s sensors (record at least values for Temperature, Conductivity and DO). 
*NOTE: Some DO sensors consume oxygen so, in this case, it’s recommended to move the sonde often to renew the water so the DO value does not decrease.*
8. Check the outset of the sensor by comparing  values measured by the Optode sensor with winkler values after measuring the bottle samples in the lab.

<!--
![Taking samples for Winkler analysis during ballasting in the glider tank at PLOCAN facilities.](/images/winkler-ballasting.png)
-->

:::{figure-md} winkler-ballasting
<img src="/images/winkler-ballasting.png" alt="Winkler calibration during balasting" class="bg-primary mb-1" width="400px">

Taking samples for Winkler analysis during ballasting in the glider tank at PLOCAN facilities.
:::

(air-pressure-effects)=
## Effects of atmospheric pressure during calibration

During the above procedures it is important to note that the equilibrium saturation oxygen concentration (C<sub>sat</sub> i.e. {cite:t}`GarciaGordon1992`) is expressed relative to 1 atmosphere.
This solubility parametrisation is described as having an RMS error of 0.3 \% (± 1.01 μmol kg<sup>-1</sup>).
The pressure effects can be significant, at 10 <sup>o</sup>C a change in local air pressure between 990 and 1010 hPa changes the equilibrium concentration by 5.4 μmol kg<sup>-1</sup>.
The quality of the local air pressure measurements during calibration is worth considering.
{cite:t}`Ponte2003` estimated the overall uncertainty for ECMWF products to be typically less than 3 hPa over most of the ocean.
This is equivalent to a 0.9-1.1 μmol kg<sup>-1</sup> error in C<sub>sat</sub>.

:::{figure-md} pressure_effect
<img src="/images/pressure-effect.png" alt="Effect of sea level pressure on the equilibirum saturation oxygen concentration (C<sub>sat</sub>)" class="bg-primary mb-1" width="400px">

Effect of local air pressure on the equilibrium saturation oxygen concentration (C<sub>sat</sub>) at 10 <sup>o</sup>C.
:::
