The Renewable Energy and the Smart Grid [(NZ GREEN Grid)](https://www.otago.ac.nz/centre-sustainability/research/energy/otago050285.html) project's Household Electricity Demand Study data includes:

 * 1 minute electricity power (W) data for c 40 households in NZ monitored from early 2014 using [gridSpy](https://gridspy.com/) monitors on each power circuit (and the incoming power);<img src="Heat_Pump_meankWperminBySeason.png" alt="Heat Pumps" title="Heat Pump season demand" style="float:right;width:250px;"/>
 * Occupant time-use diaries (focused on energy use);
 * Occupant, dwelling & appliance surveys. The survey used was identical to that used in [https://ourarchive.otago.ac.nz/handle/10523/5634](https://ourarchive.otago.ac.nz/handle/10523/5634). The  [pdf of the survey schema](EC2HouseholdSurveyAsUsedInGG.pdf) should be [read alongside](https://github.com/CfSOtago/GREENGridData/issues/45) the labels in [publicData](https://github.com/CfSOtago/GREENGridData/tree/master/publicData) when using the household attribute data file. The question numbers match and the pdf contains the item codes (which are [not always self-explanatory](https://github.com/CfSOtago/GREENGridData/issues/46)).

This data has been cleaned and anonymised using the code in this [R package](https://github.com/CfSOtago/GREENGridData/) to produce the 'safe' dataset available from the [UK Data Service](http://reshare.ukdataservice.ac.uk/853334/). *None* of the data is held in the R package so *none* of the code here will work unless you also have access to the data. 

# Accessing the data

The data is archived as:

 * Anderson, Ben and Eyers, David and Ford, Rebecca and Giraldo Ocampo, Diana and Peniamina, Rana and Stephenson, Janet and Suomalainen, Kiti and Wilcocks, Lara and Jack, Michael (2018). [New Zealand GREEN Grid household electricity demand study 2014-2018](https://dx.doi.org/10.5255/UKDA-SN-853334). [Data Collection]. Colchester, Essex: UK Data Service. DOI: [10.5255/UKDA-SN-853334](https://dx.doi.org/10.5255/UKDA-SN-853334)

You will need to register for a (free) UK Data Service account before you can download the data. Staff at UK universities should be able to use their institutional login to do so. Users from outside the UK will need to use a [specific form to request a UK Data Service user id](https://beta.ukdataservice.ac.uk/myaccount/credentials). Once registered & logged in you should be able to download the data.

Please document any errors, problems or queries by raising a [github issue](https://github.com/CfSOtago/GREENGridData/issues) and we will try to respond.

## Terms of Use

This is _not_ open access data. It is licensed as _Safeguarded_ data under the [UK Data Archive End User Licence conditions](http://reshare.ukdataservice.ac.uk/legal/#Safeguarded). You will need to agree to these T&Cs before downloading the data.

We also encourage you to log your (intended) data usage via https://github.com/CfSOtago/GREENGridData/issues/38. This is not a requirement of re-use but it helps us to justify both continuing to improve the data and also releasing future datasets.

## Version 1 - September 2018

Version 1 of the [data archive](https://dx.doi.org/10.5255/UKDA-SN-853334) includes:
 
 * powerData.zip: 1 minute power demand data for each circuit in each household. One file per household;
 * ggHouseholdAttributesSafe.csv.zip: anonymised household attribute data;
 * checkPlots.zip: 
   - simple line charts of mean power per month per year for each circuit monitored for each household. These are a useful check;
   - tile plots (heat maps/carpet plots) of the number of observations per hour per day. Also a useful check...
 * PDF snapshots of the _live documentation_ found below. 

### Documentation

 * [Research data overview](overviewReport_v1.0.html) report;
 * [Household attribute data](householdAttributeProcessingReport_v1.0.html) processing and documentation report;
 * [Household electricity demand data](gridSpy1mProcessingReport_v1.0.html) processing and documentation report;
 * [Household electricity demand outlier and negative power values](gridSpy1mOutliersReport_v1.0.html) report;
 * How to impute total household demand from the measured circuits (***don't just sum them all!***):
      * Based on [circuitsToSumv1.0.csv](reportTotalPower_circuitsToSum_v1.0.html) (deprecated)
      * Based on [circuitsToSumv1.1.csv](reportTotalPower_circuitsToSum_v1.1.html) - see [table of circuits to sum in each dwelling](https://github.com/CfSOtago/GREENGridData/blob/master/publicData/circuitsToSum_v1.1.csv).

> NB: Version 1 of the data package does not include any time-use diary data. 

### Known Problems

 * rf_15 & rf_17 grid spy files are in the archive but should not be. Users should remove them. [See further details...](https://github.com/CfSOtago/GREENGridData/issues/19)
 * For others see our [issue list](https://github.com/CfSOtago/GREENGridData/issues?q=is%3Aissue+label%3AdataIssue)
 
# Accessing and using the R code

The [GREEN Grid Data R Package](https://github.com/CfSOtago/GREENGridData) can be forked, cloned or installed as an R package. Amongst other things it contains the following folders:
  * [_reshareDataProcessing_](https://github.com/CfSOtago/GREENGridData/tree/master/reshareDataProcessing) - R/Rmd script examples to show how the clean anonymised data can be analysed.
  * _originalDataProcessing_ - R scripts to process data and generate data quality reports. These will not run without access to the original study data but you can review them to understand why the anonymised data looks the way it does;
  * _docs_ - the data archive documentation published via the [github pages](https://cfsotago.github.io/GREENGridData/) that you are now reading. These were created sing the code in the _originalDataProcessing_ folder.

We encourage [feedback](https://github.com/CfSOtago/GREENGridData/issues) and [contributions](https://github.com/CfSOtago/GREENGridData/pulls) but inevitably #[YMMV](https://en.wiktionary.org/wiki/YMMV).

We also encourage you to log your (intended) data usage via https://github.com/CfSOtago/GREENGridData/issues/38.

# Publications to date

 * Suomalainen, Kiti, David Eyers, Rebecca Ford, Janet Stephenson, Ben Anderson, and Michael Jack. 2019. ‘[Detailed Comparison of Energy-Related Time-Use Diaries and Monitored Residential Electricity Demand](https://doi.org/10.1016/j.enbuild.2018.11.002)’. Energy and Buildings 183: 418–427.
 * Anderson, Ben and Eyers, David and Ford, Rebecca and Giraldo Ocampo, Diana and Peniamina, Rana and Stephenson, Janet and Suomalainen, Kiti and Wilcocks, Lara and Jack, Michael (2018). [_New Zealand grid household electricity demand study 2014-2018_](https://dx.doi.org/10.5255/UKDA-SN-853334). [Data Collection]. Colchester, Essex: UK Data Service. DOI: [10.5255/UKDA-SN-853334](https://dx.doi.org/10.5255/UKDA-SN-853334)
 * Jack, Michael & Suomalainen, Kiti (2018). [Potential future changes to residential electricity load profiles – findings from the GridSpy dataset](http://hdl.handle.net/10523/8074). NZ GREEN Grid Technical Report, University of Otago.
 * Jack, M. W., K. Suomalainen, J. J. W. Dew, and D. Eyers. 2018. “[A Minimal Simulation of the Electricity Demand of a Domestic Hot Water Cylinder for Smart Control]((https://doi.org/10.1016/j.apenergy.2017.11.044)).” Applied Energy 211: 104–12;
 * Stephenson, Janet, Rebecca Ford, Nirmal-Kumar Nair, Neville Watson, Alan Wood, and Allan Miller. 2017. “[Smart Grid Research in New Zealand–A Review from the GREEN Grid Research Programme](https://doi.org/10.1016/j.rser.2017.07.010).” Renewable and Sustainable Energy Reviews 82 (1): 1636–45;
 * Suomalainen, Kiti, Michael Jack, David Byers, Rebecca Ford, and Janet Stephenson. 2017. “[Comparative Analysis of Monitored and Self-Reported Data on Electricity Use](https://ieeexplore.ieee.org/document/7977557/).” In Environment and Electrical Engineering and 2017 IEEE Industrial and Commercial Power Systems Europe (EEEIC/I&CPS Europe), 2017 IEEE International Conference on 6-9 June 2017. IEEE;
 * Giraldo Ocampo, Diana. 2015. “[Developing an Energy-Related Time-Use Diary for Gaining Insights into New Zealand Households’ Electricity Consumption](http://hdl.handle.net/10523/5957).” Master’s thesis, Centre for Sustainability: University of Otago.
