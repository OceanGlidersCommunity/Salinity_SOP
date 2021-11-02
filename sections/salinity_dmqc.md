# Delayed Mode Quality Control

## Correction for dynamic errors
Salinity derived from temperature and conductivity is prone to dynamic errors that are a result of profiling in a dynamic environment characterised by spatial temperature and salinity gradients. 
While dynamic errors in conductivity and temperature are usually small relative to natural variations, they can compound into large relative errors in derived salinity. 
This is because, in many regions of the ocean salinity does not vary as much as conductivity and temperature. 
Dynamic errors can, for example, create false density instability in profiles and false variation in mixed layer depths. 
This is particularly important in beta oceans, where density is set by salinity variations (e.g. in polar regions; Gulf of Oman).
Both pumped, unpumped, electrode-based and inductive CTDs that measure conductivity and temperature (see section 2), are prone to dynamic errors that can be greater than the instrument calibration accuracy and therefore need to be corrected for (Johnson et al. 2007; Woo and Gourcuff, 2021).

Four main sources of error are (i) spatial offsets in sensor location on the profiling platform, (ii) different sensor time-responses of the thermistor, conductivity sensor and pressure sensor, (iii) timestamping of sensor measurements, and (iv) thermal-inertia effect. 

We suggest applying the thermal mass correction method similar proposed by Garau et al. (2011) and developed by Lueck et al (1990) and Morrison et al (1994), to account for the delayed temperature equilibration of the conductivity cell. (see Chapter 5 DMQC). 
The correction depends on the speed with which the water flows through the conductivity cell. 
For pumped CTDs, the flow through the CT cell is known and constant, thus corrections like Garau et al. (2011) can be simplified to use only constant thermal-inertia corrections, however these corrections are generally worse around the thermocline: 1) the glider speed may change as a result of stratification; 2) there is a rapid vertical change in temperature and/or salinity. 
In the case of unpumped CTDs, for increased accuracy, we recommend using the modelled velocity of the glider through the water to estimate the flushing speed of the CT cell which can be used to correct for the temperature offset (reference to Depth Averages Current (DAC) SOP). 
The flight model can be improved by following pre-deployment and piloting protocols as per the DAC SOP. 
The amplitude of the error,  ɑ,  and the time offset constant, 𝜏, are used to correct for thermal mass offset. 
These parameters can be estimated by minimizing the difference between up and down dives in temperature and salinity space, although minimizing in salinity and depth space can be preferable in some environmental conditions (with different stratification characteristics) and was also applied by Morrison et al (2004). 
One can elect to apply this minimization per dive or over the whole mission. 
Per dive tends to give cleaner data but can sometimes mask real signals (if regressed in depth, z). 
Applying the minimization per mission makes the assumption that the shape of the sensor doesn’t change and that the model is representative and so only one set of parameters is needed to represent a whole mission. 
In cases in which the hydrodynamic coefficients change (e.g. if there is biofouling), per dive or multiple dive segments may be a preferable choice. 

It should be noted that because such corrections require interpolating to a regular time grid, the (1) interpolation method and (2) correction scheme, can introduce energy at specific frequencies in post processing which can bias any form of spectral analysis for TS data down the line (ref to RBR Legato Dynamic Corrections report - https://oem.rbr-global.com/floats/files/5898249/34668603/1/1586804683000/0008228revA+Dynamic+corrections+for+the+RBRargo+CTD+2000dbar.pdf).  

The corrections we propose are therefore:

### Spatial alignment correction
Apply offset to account for the spatial offset in sensor location on the platform, if needed.

### Temporal alignment
Align temperature, conductivity and pressure sensors in time.

### Interpolate to consistent timestamps
Interpolate to consistent timestamp between sensors.

### Apply correction for conductivity cell thermal inertia
Initially, the effects of thermal inertia can be visualised as a scatter plot of temperature and salinity, colored by dive phase (whether the glider is performing a dive or a climb). 
The effectiveness of the correction can then be checked similarly. 
Often, the correction is not perfect: the remaining error can be reported as a RMSE of the difference between dives and climbs, as in Giddy et al., 2021. 
