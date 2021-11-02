# Introduction

This standard operating procedure (SOP) document for dissolved oxygen (DO) aims to guide the user through the steps necessary to collect good quality dissolved oxygen data using ocean gliders for both real time and post deployment data streams.

*Table 1: List of the known sensor/glider combinations. We aim to cover all combinations in this document.*

| Sensor / Glider  |  Slocum |  Autosub/ ALR (NOC) |  Seaglider | Deepglider  |  SeaExplorer |  Spray |  Information |
|---|---|---|---|---|---|---|---|
| Aanderaa 3835, 4330, 4330F, 4831, 4831F and 5013 optodes  | X |   | X | X |   |   | [Link](https://www.aanderaa.com/productsdetail.php?Oxygen-Optodes-2) |
| RINKO-II  | X |   |   |   |   |  | [Link](https://www.jfe-advantech.co.jp/eng/ocean/rinko/rinko22d.html) |
| RINKO- AROD FT  |   |   |   |   | X |   | [Link](https://www.jfe-advantech.co.jp/eng/ocean/rinko/rinko-ft.html) |
| SBE 43 and 43F  |   | X | X |   | X |   | [Link](https://www.seabird.com/sbe-43-dissolved-oxygen-sensor-with-titanium-housing-mcbh-connector-0-5-mil-profiling-membrane-standard-43-plenum/product?id=54627923854) |
| SBE 63  |   |   |   |   |   | X | [Link](https://www.seabird.com/oxygen-sensors/sbe-63-optical-dissolved-oxygen-sensor/family?productCategoryId=54627869933) |
|  RBRcoda T.ODO |   |   |   |   | X |   | [Link](https://rbr-global.com/products/sensors/rbrcoda-odo) |
|  Contros Hydroflash (1) |   |   | X |   |   |   | [Link](https://www.kongsberg.com/globalassets/maritime/km-products/product-documents/hydroflash-accurate-fast-and-versatile-oxygen-optode/Download) |

(1)The advanced, optical sensor is based on the principle of fluorescence quenching. Contros are no longer in operation, the sensors cannot be calibrated so they are likely to become obsolete in the future.

## Aanderaa Optodes
Aanderaa optodes are the most widely used oxygen sensor on ocean gliders and a large body of work has now been dedicated to their characterisation (e.g. {cite}`Bittig2018`).
These sensors are based on the oxygen luminescence quenching of a platinum porphyrin complex (fluorescent indicator) that is immobilized in a sensing foil. 
These offer low power consumption, good long-term stability, low fouling sensitivity while not being sensitive to H2S or freezing.
Aanderaa optodes have seen several important developments since they were introduced in 2002, with various hardware and firmware revisions which we outline below (shown in {numref}`optodes`).

### Hardware design: blue or black
While mostly cosmetic, the colour of the optode is a useful short-hand for the two main optode designs.
The 3835 and 4835 optodes both feature a black housing with the temperature sensor integrated into the base of the sensor near the connector. 
This results in a large thermal mass and increases the response time of the temperature sensor significantly. 
The blue 4330 and 4831 sensors move the thermistor next to the sensing foil which results in much improved performance of the temperature sensor.
with an increase in accuracy to 0.03$^{\circ}$C from 0.05$^{\circ}$C, and time-response reduction to <2 seconds rather than ~10 seconds {cite:p}`Aanderaa2018`. 
All optodes other than the 4831 use a 10 pin Lemo connector, these connectors can’t be connected when wet and are prone to crevice corrosion. 
The 4831 is therefore recommended with it’s Subconn wet-pluggable connector.
Older optode versions (3830) have a titanium housing in the same form factor as the 3835. 
Some early Slocum gliders were delivered with optodes of type 5013, these are identical to the 3830.

### Foil type: F or standard
Most optodes use the PreSens PSt3 foil (PreSens - Precision Sensing GmbH), these have as standard a black opaque protective layer protecting the pink sensing layer.
For glider applications the “F” type foils are typically preferred as these remove the opaque layer which results in much faster diffusion across the foil, and therefore faster sensor response ($\tau$ = 8 s compared to ~ 25 s {cite}`Bittig2014`). 
However, removal of the protective layer makes the foil more susceptible to UV radiation, and is known to reduce the sensor stability, especially when exposed to strong sunlight.
Newer 4330F and 4831F optodes (Since July 8th 2018) use an improved formulation of the Presens fast foil which are less sunlight sensitive and have much lower noise levels. These can be identified by their white appearance. 
It is recommended that older F-type instruments (with the pink foils) are upgraded with these improved foils. 
Otherwise foils should typically not be replaced unless mechanically damaged (light intrusion) as older foils perform better, with less drift than new ones.

### Calibration equation and firmware versions
The way optode foils are initially calibrated by Aanderaa, and how the measured values are processed by the optode varies between different optode versions.
The optode illuminates the sensing foil with both a red and blue LED. 
Since the red light does not produce fluorescence in the foil the phase measurements are obtained from the difference between the blue (P1) and the red (P2) excitation.

P_T = A(T) + (P1 - P2) · B(T)

Where P_T is the temperature compensated phase (known as ‘TCphase‘). 
A and B are temperature dependent coefficients which allow for temperature compensation of the phase measurement. 
However for most 4330, 4831 and 4835 optodes these are not used, such that A(T) = 0 and B(T) = 1. 
This can be confirmed by communicating with an optode and inspecting the ‘PTC0Coef‘ and ‘PTC1Coef‘ properties. 
For older optodes (4330 serial numbers < 1000) the temperature compensated phase is then used to calculate ‘calphase‘ (P_c). 
For newer optodes P_T = P_c. Similarly older optodes have their calibration (and recalibration) applied though the modification of the ‘PhaseCoef‘ coefficients. 
On later optodes the calibration is not applied in phase space, but on the oxygen concentration though the use of the ‘ConcCoef0‘ and ‘ConcCoef1‘ coefficents (‘PhaseCoef0‘ and ‘PhaseCoef1‘ are set to zero and 1 respectively). 
Consult your optode calibration sheet and confirm which terms are being used.
There are three different calibration equations used to convert the measured phase to oxygen equations:
The “Mk1” equation used by the older 3835 optodes uses a 5x4 matrix of coefficients. 
The “Mk2” equation is used by non-multipoint calibrated 4330(F) and 4835 optodes, and uses a 2x14 matrix (FoilCoefA and FoilCoefB) together with a 2x27 matrix for the polynomial degree, this second matrix is the same across all of these type optodes. 
Newer multipoint calibrated optodes use the Stern-Volmer (SVU) equation proposed by {cite}`Uchida2008` which has 6 terms.
Non-multipoint foil calibrations are based on a common characterisation of a production batch. 
Multipoint calibrations consist of 40 calibration points across a range of concentrations and temperatures and offer improved accuracy and should be preferred when purchasing these sensors.
Consult your optode foil calibration document to verify which version your optode is using. 
Understanding these differences in how the calculations are performed is important when recalculating oxygen from the phase readings, such as when compensating for lag.
Regardless of the optode version, oxygen can be recalculated from calphase using the approach of {cite}`Uchida2008`.
During the initial months of storage/use a Foil maturation process occurs resulting in lower readings by several %. 
The maximum observed maturation induced drift on more than 1000 sensor has been 8 % for sensors with non-factory pre-matured WTW foils (model: 4835, 4531 and 5730 Steinsvik) and 6 % for sensors with factory pre-matured PSt3 foils (model: 4330, 4831, 5331 hadal). 
During/between field deployments there are possibilities for end users to post-adjust the sensors either by a one-point air-saturation adjustment or by taking reference samples (e.g. water samples and Winkler titration) and/or using a well-calibrated sensor in parallel. 
If done correctly such an adjustment should result in an absolute accuracy of around 1 % for multipoint calibrated sensors (model: 4330, 4831, 5331 and 5730) and 3 % for two-point calibrated (model: 4835, 4531), see below for more information about factory calibrations. 
The drift will decrease over time so that during the second year it is not likely to be more than 1-2 %. 
After this it should be less than 0.5 % per year, unless the foil is mechanically damaged (Aanderaa).

:::{figure-md} optodes
<img src="/images/AaanderaasensorsAll1.png" alt="Aandera Optodes" class="bg-primary mb-1" width="400px">

Suit of smart optodes sensors. Oxygen sensors are indicated by red arrows.
:::

## RBR coda T.ODO
The RBRcoda T.ODO uses the same foils and methods as the 4831 and 4831F so everything above specified for the 4831 will also apply to those instruments as well.
RBR refers to the standard optode (~30 s $\tau$) foil as “slow” and the fast (~8 s) as the standard.
They also use further foil design (~1 s response) which they call fast. 
The RBR sensor has a smaller form factor than the Aandera optodes, but is overall more similar to a 4831 with the temperature sensor very closely located to the sensing foil. 
This sensor has recently been implemented in gliders, and little is known about their performance.

## JFE Advantech RINKO
AROD-FT sensor (RINKO JFE) is used for the SeaExplorer gliders (Alseamar) and for some Argo floats (small size and low power consumption) (see {numref}`ARODFT`). 
This sensor is based on the optical (phosphorescence) principle which is now widely known as a remarkably fast response oxygen sensor (below 1s) with a high accuracy of 2 $\mu$mol/kg. 
This sensor used a multi-points calibration (16 points with 4 temperatures and 4 DO concentrations). 
In this procedure, the DO reference standards are produced by saturing the primary mixtures with DO concentrations of approximately 4%, 10%, 17% and 25% respectively (certified by the National Metrology Institute of Japan). 

<!--
![AROD-FT sensor mounted on a SeaExplorer glider (credit: ALSEAMAR) \label{fig:ARODFT}](/images/ARODFTSensor.jpg)
-->

:::{figure-md} ARODFT
<img src="/images/ARODFTSensor.jpg" alt="AROD-FT sensor" class="bg-primary mb-1" width="400px">

AROD-FT sensor mounted on a SeaExplorer glider (credit: ALSEAMAR)
:::

The DO concentration is calculated from the {cite}`Uchida2010` equation with 9 calibration coefficients. 
A second equation is used to take into account the pressure effect (linear equation with one calibration coefficient). 
Finally, the salinity-compensated DO concentration is calculated by multiplying the factor of the effect of salt on the oxygen solubility {cite}`BensonKrause1984` and {cite}`GarciaGordon1992`.
This is similar to procedures used on other optodes.

<!--
![Oxygen saturation from a Rinko AROD-FT on a SeaExplorer glider in the Bornholm Basin (credit: Voice of the Ocean Foundation and University of Gothenburg). \label{fig:samba}](/images/SAMBA.png)
-->

:::{figure-md} samba
<img src="/images/SAMBA.png" alt="Oxygen saturation from a Rinko AROD-FT on a SeaExplorer glider in the Bornholm Basin" class="bg-primary mb-1" width="500px">

Oxygen saturation from a Rinko AROD-FT on a SeaExplorer glider in the Bornholm Basin (credit: Voice of the Ocean Foundation and University of Gothenburg).
:::

Recent deployments of a SeaExplorer glider equipped with an AROD-FT sensor have shown long-term stability (low drift over time) but with a significant offset observed during sections in the Ligurian Sea (on average 10-15 $\mu$mol/kg). 
Deployments in the Bornholm Basin have shown good agreement across a wide range of oxygen concentrations with a nearby BOOS monitoring station (see {numref}`samba`. This sensor was a recent acquisition and had little opportunity to drift in storage.

## Clark electrode polarographic sensor (SBE 43, SBE 43F and SBE 63)
The SBE 43, SBE 43F and SBE 63 are individually calibrated with a calibration drift rates of less than 0.5% over 1000 h of operation. 
These sensors have been used in Seagliders and Spray and also in morrings and Argo floats. 
Sensors are designed for use in a CTD’s pumped flow path, providing optimal correlation with CTD measurements. 
Elapsed time between the CTD and associated oxygen measurement is easily quantified, and corrected for, in post-processing. 
The black plenum and plumbing’s black tubing blocks light, reducing in-situ algal growth. 
Response time $\tau$ varies from 2-20 sec depending on the membrane thinness, ambient water temperature and flow rate. 
Drift thresholds for sensor performance should be established prior to data collection, to determine how often instruments should be serviced, validated, and returned to Sea-Bird for a full service and calibration. 
It is recommended to do validation in the lab before and after deployment/recovery and while the sensor is in the water (if possible). 
For this task, Winkler samples or a clean, calibrated reference sensor will be required. (Information from https://www.seabird.com) 

