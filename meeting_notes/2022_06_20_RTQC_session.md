# T&S Real Time Quality Control User Meeting

### Date: June 20 2022, 15:00 - 16:30 CEST

Session chair: Soeren Thomsen
Notes: Callum Rollo

# Participants
Callum Rollo, Victor Turpin, Isabelle Giddy, Corentin Guyot (Ifremer), Soeren Thomsen, Justin Buck (NOC), Pierre Testor (LOCEAN/CNRS, France), Joan Mateu Horrach Pou (UiB), Gui Castelao (SCOOT Science), Joe McGovern (Marine Institute, Ireland), Garry Glass, Antonio Bussani (OGS), Yves Poncon (LOCEAN), Emma Slater (NOC), Dave Hebert (BIO/DFO Canada)
Thania Papapostolou (HCMR Greece)
Angel Ruiz-Angulo (University of Iceland), Anh Tran(MEDS, DFO Canada), Ali Aydogdu (CMCC), Nikolaos Zarokanellos (SOCIB), Kimmo Tikka (FMI)


# Agenda
1) [Presentation](https://github.com/OceanGlidersCommunity/Salinity_SOP/blob/main/meeting_notes/2022/WS3%20-%20Focus%20on%20Real%20Time%20data%20management%20of%20Temp%20and%20Sal%202.pdf) by Victor Turpin: Real Time Data Management of Temperature and Salinity
2) [OceanGliders Salinity SOP](https://oceangliderscommunity.github.io/Salinity_SOP/README.html#) by Soeren Thomsen
3) Live Notes via HackMD by Callum Rollo
4) Collection of issues by users
5) Discussion: Community feedback on the data flow ?

Where are your difficulties in providing gliders data to Coriolis GDAC ? 
How can we improving the Real Time data flow ? Where are the bottlenecks ? 
Shall we extend the required metadata to make the most of real time temperature and salinity ?
Specific requirement from the data assimilation community ?
How to improve the quality of the Real Time data ? Thermal lag correction ? Real Time QC ?




# Meeting notes

### Victor Turpin presentation

[Link to presentation pdf](https://github.com/OceanGlidersCommunity/Salinity_SOP/blob/main/meeting_notes/2022/WS3%20-%20Focus%20on%20Real%20Time%20data%20management%20of%20Temp%20and%20Sal%202.pdf)

GROOM 1 Core idea: multiple glider groups that push raw data and metdata to DACs. They use a common format (now EGO, later OG1.0). Data are pushed to data aggregators then onward into data products. Still what we use now

1. Glider at sea send raw data to the "landstation". This is on the PI/operator. 
2. Data sent from there to the DAC with metadata
3. At DAC they are processed into a common format
4. Sent from DAC to GDAC

GTS is seperate from thsi process

**Questions**
Is there a sampling strategy that serves need of specific comunity? Should these needs feed into glider piloting strategy? What do modellers/forecasters want?
How do we reference the initial CTD cast in the file? How is it used for QC?
What metadata are required for optimal use of T&C in real time?
New sensors like RBRLegato3. Pumped vs unpumed? Input from new teams. e.g RBR requires factor of 10 conversion
Difficulties to convert from sbd/tbd to .m or .dat. These are what coriolis use. These are converted formats.
How do we get to GTS? Procedure? Format?

Existing sensors and gliders still have their own conversion foibles e.g. pressire from slocums needs multiplying by ten and position from slocums is telemetered in degrees with decimal minutes.

.m/.dat -> there are executables to convert sbd/tdb (dbd/ebd, mbd/nbd). There is new ones for G3 or so...

Real time corrections? Thermal lag? 


New BUFR template for gldiers for use on the GTS is being tested here https://github.com/wmo-im/BUFR4/issues/16 

### Salinity SOP by Soeren

Soeren: some questions raised by Victor answered already by the SOP. Still many unanswered though! New collaborators welcome.

This shows sensors and platforms list. Has been reviewed by the community.

If anything is not clear, please make a comment

Lots of work needed on the [real time section of the SOP](https://oceangliderscommunity.github.io/Salinity_SOP/sections/salinity_rtqc.html)

Not completed yet. Once it is complete it will be submitted to the Ocean Best Practices System (OBPS) to get a DOI.

After that, will write a paper in Frontiers (shorter than the SOP) to get peer review and authorship.

[Data sharing section](https://oceangliderscommunity.github.io/Salinity_SOP/sections/data_sharing.html) could use improving. Could like to some guidelines. Please jump in from the data management team.

Check out the [Issues](https://github.com/OceanGlidersCommunity/Salinity_SOP/issues) for ideas of what you can contribute.

Isabelle: DMQC section. There are many approaches and methods. We aim to list all of these. As a second step we can make recommendations from these. It's ok to have several methods in the document.

Soeren: this is a long term project. Especially for something like thermal lag. In the long term we want ot converge on one method.

### Discussion chaired by Soeren

Justin: existing gliders have foibles (see comment in previous section). We still don't have a mechanism for someone not familiar with specific glider platform to process it


Victor: Ali Aydogdu is working in CMCC to assimilate glider data. How could glider flight be changed to improve the usefulness of this data for assimilation

Ali Aydogdu: for real time applications flying glider for needs of forecasters is not easy or clear. Targeted experimentation designed with gliders in mind can be done, but operationally, don't know where/when extreme events will occur. For reanalysis, maybe gliders can be targeted. Instead, increase collaboration. Alreayd doing great targeting boundary currents etc. **improve NRT quality control in assimilation systems**. This cna be helped by glider profiles. These are hi-res even if models improve. Cannot assimilate all profiles at once. Have ot subsample due to correlation. Some considerations on how to manage pre-processing quality check or NRT data to make these most beneficial to forecast models.

Gui: For assimilation would be useful to get subsurface locations of gliders. What if we had uncertainty of locations and parameters? Useful for assiilation? How do we simplify it? Treat as CTD? Treat as V? better to treat as uncertainty. Ali agrees.

Ali: Data assimilation is balancing problem. Assign relative errors to observations. Uncertainty estimate is a key issue we neeed to improve on.

Victor: Specific RTQC for data assimilation needs ?

Justin : the primary stakeholder of RTQC is the assimilation community

Gui: If I have a doubtful QC measure, I apply a big uncertainty. Ali agrees this is helpful

Ali: We just use the average error. No including it day by day, just one error estimate fixed in time. Doing monthly variability e.g. seasonal variation of thermocline uncertainty not daily timescales. However, this could be improved. Don't do right know because they have to information for this. Assimilation community is not advanced to the point of varying error on a per instrument per profile basis. This is not easy for keeping balance

Soeren: assimilation, how should we guide discussion? Are there best practices documents for assimilation community for glider data? Where does this fit in to the SOP ecosystem? Could be a section of Salinity SOP. Would like a living document. 2-3 pages is fine as a start

Justin: RTQC formulated by several groups (qartod, SOCIB, Ifremer etc) generally taken form other networks like Argo and applied to gliders. Suspect there are some key issues here. Gaps that only affect glider data. We need to work with met office/assimilators to find these gaps. Can't just pull in/copy from other networks.



*Point to discuss raised by P. Testor:* Ten years ago, it was not an issue because forecasting ocean models did not have good vertical resolution and it did not really matter. But now, the thermal lag errors in salinity are assimilated by them and they are visible in model outputs :-o. So there is an urgent need to do the thermal lag correction in real time for every glider profile, which is not the case today. How can we make that happen in all DACs? inclusion in the EGO processing chain?

Pierre: in future there will be better models. Need to slve thermla lag in thermocline issue

Ali: Solving thermocline is most difficult thing to assimilate. IF model doens't exactly capture location of thermocline, difference between obvs and models becomes very large. Can't correct model too much or you break balance of waters. Need more accurate extimate of interfaces. Related to thermal lag problem? From argo profiles we do not get location of interfaces between upper and lower water.

Justin: thermal lag and spatial difference between sensors, thermal lag is greater where there is strong stratifciation

Pierre: We have good NRT resolution of thermocline depth. Hysterisis of salinity data are in issue with glider going up vs down. You can detect where the thermocline is though. 

Ali: RTQC is primitive still. 1st check is against background model/observations. If deviate abve threshold they are not used in the assimilation. Rejects real spikes.

Soeren: Please make a repo and link to your QC. This would improve visibility and be a low effort step. just list what you've done in a common document. Don't reinvent the wheel! Can make a repo after this for the purpose. Wants to link this later from the SOPs, rather than doing it on a parameter level.

Ali: new to this field of glider assimilation. In oceanpredict community, there are many experienced people. Maybe can bring this effort to that commmunity in following months.


Justin: addressing these issues becomes more important as uptake increases. Important example: fall rates from XBTs, pressure sensor issues in Argo. If we don't resolve these issues are we become aware, they become more dangerous as uptake increases.

Victor: Naive question : Is there technics/procedure to apply RT correction for thermal lag for example ?

Soeren: should be possible, just need to get ad-hoc estimate of lag time. Similar to oxygen, without time delay consideration, data are unusable.


David Hebert : **The problem is that the RT is a subsample of the data** and doesn’t have the resolution where ihe previous work is on higher sampled data.

Justin: agrees with Dave. When we have worked with data operators for years, we know what data we need. Require a best practice to apply and give Met Office the data they need. Consider sampling strategies as well as data management.

Gui: One of the problems is lack of resolution for NRT. Gui isn't convinced that doing something is better than nothing. Risk that you intorduce more problems. Better to just pass it on with high uncertainty. Especially when you have very diverse sources/platorms. Easy for provider to mess up.

Soeren: Would be good to have this in the SOP!

Angel Ruiz-Angulo: I would like to follow up on that previous question, mainly on standardised techniques


Pierre: Even if the resolution is not enough, what alternative? QC flags? Right now we don't identify it.

Soeren: In regions where you expect high thermal lag, could flag? uncertain

Justin: Can flag the profiles with a "3" probably bad/needs attention (or "2" probably good). The new BUFR template has variable flags for this purpose. How do we come together and share tools? How do we enable DACs to deploy tools? Only a small part of profile that are bad in the the thermocline, just flag those as suspect, not the whole profile

Victor: In some places we don't have the full resolution. Can't we turn off sub-sampling for some profiles? Once or twice a day in regions where thermocline is not represented. Data assimilation community would benefit from this. Tricky for data management.

It is not that the thermocline is not well captured. It is, but the gradients in temperature induce errors in the computation of salinity (from cnd, pres, temp) there.

Callum : Not feasible with seaexplorer as data sets are not stored at the same place. Would require changes by the manufacturer

Dave: subsampling is for checking that sensors are working. Not feasible to send back all data, too iridium expensive.

Nikolaos/Soeren: data form pumped CTDs can be a lot better, even in thermocline


Pierre: Possible to have different vertical resolution in real time. We use this to control data volumes. Don't wantto transfer too much over iridium

Ali: Subsamping, is this an institutional practice? Sensor limitation?

Pierre: depends on model. Generally get subsmpaled data over satellite, full resolution on glider when it is physically recovered later. Deliberately subsample data to save on iridium costs. This is typically decided by the operator. Also increased surface time is risky for gliders (collisions). Costs order 1000 euro per glider per deployment

Soeren: May want to send back more data if there is a risk the glider is going to be lost to ice etc.

ALi ;: We use CMEMS data, so more processing, and it is already high resolution from data assimilation perspective.

Victor : So the issue is not the sampling strategy but the RTQC and the error estimate.


Pierre: glider data is hi-res vertically and horizontally

Ali: Issue recently is surfacing of gliders. Some do not surface every dive. This creates issues linking surface with the deep. End up using deep obvs to correct shallow obvs. Better to subsample by profile: no need to assimilate every dive

Justin: how about we work with manufacturers to correct on board?

Pierre: what method would we use? Need to get agreement on the best method. Need to get some demonstration on what method is best. Use many on one dataset and compare them.

Soeren: Isabelle has done comparison of methods in the SOP. Someone needs to test this on a real dataset though...

Isabelle: Seaglider does do on server processing after data are transferred. But you often have to recorrect after this. But at least this is version one. Done by Seaglider basestation software to correct thermal lag

Soeren: Should we make recommendations of sensors? As scientists we should be honest and say "we have lots of issues with this sensor". Tried very hard to get people to write on a sensor, but there were so many issues! Couldn't find anyone to write on it

Pierre: A bit dangerous. Not political to make a specific recommendation. Need to be careful. Can depend on the user. Fine to criticise a sensor though! Clearly explain the issues

Soeren: If you've had issues, should tell the community that.

Jusin: If you create a monopoly, they will price gouge. This has happened before (no names). It is better ot help manufacturers improve their sensors.

Soeren: manufacturers can also contribute to the SOPs. They have great expert knowledge on these systems. This is useful, but shouldn't stray into advertising from these companies.

Victor: land station >> data assembly centre. If you choose to use Coriolis as a DAC, what are the difficulties you are facing to send data and metadata to the DAC before you process the data. How can we help you make this easier? This has been slow, how can we help.

Isabelle: Have tried ot work with them before to get gliders onto GTS but have not managed Not sure what the issue is. It's a slow process, got lost? Could you simplify the number of variables to send?

Victor: T&S would be easier for metadata. Maybe this could be an approach to start from these variables only. Make this automatic? Improve with new sensors going forward. We are doing it mostly for data assimilators, so this focus could be good as they are most used variables.

Callum: could you take it from ERDDAP?

Victor: GTS and GDAC are seperate. Only th met office can push to GTS. Coriolis, the DAC, send it to Met office France, which push it to GTS. ERDDAP could be used to aggregate data, but not all glider group can make one though. It makes it very easy if you can do one. Too much for smaller groups

Justin: ERDDAP gives lots of options. Once OG1.0 is on that, it will be great. GTS is being workd on as an output format from ERDDAP. Gap is the best practice is flow from DACs to GTS. Need to establish these pathways first. BODC would feed to GDAC and Met Office from the ERDDAP in one push. This simplifies it into one pathway. Need to rationalise this as a community.

Corentin: Isabelle's suggestion is good. What takes time is oxy and chl as they need calibration constants etc. But T&S are easy to decode. We can work to do this first. In parallel work on more complex ones. 

Soeren: We'll submit this SOP soon, so please contribute




