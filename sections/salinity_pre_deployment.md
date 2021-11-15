(pre-deploy)=
# Pre deployment protocol

(sensor-calib)=
## Sensor Calibration
Most users send their CT-sensors to manufacturers to get high quality/high precision calibrations. 
Few organizations have the ability to do in-lab conductivity and temperature calibrations, especially for the unpumped CTD found on Seagliders because of its direct integration into the glider fairing (see {numref}`unpumped`).

For the RBR*legato*<sup>3</sup> sensor with an inductive cell, the calibrations can only be done in the field or by using the SeaExplorer’s coefficients that correct the influence of the vehicle on the sensor’s inductive field. 
The accuracy of these coefficients is unproven. 
The recommended strategy is to sample deep CTD in proximity, which becomes problematic in shallow dynamic shelf sea waters. Nevertheless, correction is simple: a scaling factor is applied to conductivity.

Users should note that conductive cells (mostly unpumped, but the pumped ones as well to an extent) change conductivity calibration (again just a scaling factor) when they take a hit, because it can change the shape/volume of the conductivity cell. There is increased risk for this to occur during deployments by crane from large vessels.

(antifoul)=
## Antifouling
Materials immersed in water experience a series of biological and chemical processes, resulting in the formation of complex layers with attached organisms. 
Biofouling that can affect salinity through 1) blocking the CT valve (see {numref}`pump-malfunction` ) and 2) impacting the flight model, which estimates the glider’s speed assuming a steady flight in still water. 
This glider’s speed is then used to correct the thermal-inertia effects of unpumped CT instruments (see {numref}`dynamic-error-correction`). Biofouling will tend to increase the drag coefficients and decrease the lift coefficients of the flight model. 
A time-dependent/ incremental flight model can handle these effects. 
In the correction proposed by {cite}`bennett_determining_2019`, the coefficients of every profile are calculated and can correct the effects of the biofouling on the flight model. 
In GEOMAR / Gerd Krahmann implementation, if there is a 5% increase in the drag coefficient over the deployment, then it is treated as time dependent and the optimization of the flight parameters is handled accordingly.

Pre-mission, if one expects biofouling on the glider platform (e.g. in regions of very high productivity), one can put zinc-oxide cream over the seams of the glider so that there are fewer locations with tiny turbulence where larvae have time to attach. During post mission procedures, in order to eliminate biofouling effects for the next mission and clean the GPCTD, it is suggested to be thoroughly rinsed in (with a special water dispenser) and out (with a water jet) with fresh water. Then, the antifouling solution can be inserted with a special dispenser (e.g. syringe) into the plumbing of the sensor.

:::{figure-md} example-biofouling-on-glider
<img src="/images/socco_biofouling_example.png" alt="Seaglider_with_biofouling" class="bg-primary mb-1" width="400px">

Biofouling example from a long deployment in the Subtropical Zone in the Southern Ocean (Image credit: Sebastiaan Swart/CSIR-SOCCO).
:::

:::{figure-md} example-biofouling-on-GPCTD
<img src="/images/Evi-HCMR_glider_3.jpg" alt="GPCTD_with_biofouling" class="bg-primary mb-1" width="100px">

Biofouling on the GPCTD intake after 36 days in the Aegean Sea (Image credit: Evi Bourma).
:::


