plague-UK-1665
==============

Recent analysis, based on time series analysis of historic and recent records of plague epidemics, have identified 
surprising discrepancies between between the characteristics of past and present epidemics that we had
so far been attributing to plague. For example, in [this paper][1] Mark Welford and Brian Bossak show that the seasonal
peaks of mortality of the medieval Black Death and current laboratory-confirmed cases differ significantly.
Have we been wrong in attributing the Black Death epidemics to the bubonic and pneumonic plague? 

This question remains open, and we are simply going to illustrate here how mechanistic models could be used to
provide further insight into the characteristic of present and historic epidemics. We will be working on two time
series of the 1665 epidemic in the UK, each indicating the monthly number of deaths caused by plague in London
and Eyam. Contrasting these two cases is not only interesting due to the population size difference between London 
and Eyam, that had respectively 460000 and 350 inhabitants at the beginning of the epidemics, but also due to the
[very particular story of the city of Eyam][2]. As inhabitants started to die, the clergyman William Monpesson decided 
in agreement with Thomas Stanley to isolate the village in order to protect the neighbouring cities of Northern 
England. During one year, Eyam lived in quarantine. Food was cautiously supplied to the village so no one starved,
but at the end of the epidemic, one year later, 250 people had died. 


This story sheds a particular light on the following time series that can be found
in the *Bills of Mortality*.  Since 1932, these records had been filled by English doctors who had been asked to 
identify the deaths due  tuberculosis, small pox, measles, French pox, and plague:

![data](https://raw.github.com/JDureau/plague-UK-1665/master/images/data.png?login=JDureau&token=c5b1e3d648591265b128978f10a0bcee)


To analyse this dataset we use a simple SI model, meaning the individuals are either infected with plague or 
susceptible to become infected.
Seasonal forcing is introduced, which timing and amplitude are being estimated. At last, we consider that life
expectancy with plague is between 1 and 10 days. Due to the inherent uncertainty
in data collection, observational noise needs to be accounted for when modeling the dynamic of these epidemics
as well as demographic stochasticity. The resulting estimates of the transmission potential of plague in each city, as
well as the death rate with plague, are the following:

![data](https://raw.github.com/JDureau/plague-UK-1665/master/images/post.png?login=JDureau&token=cf7c103e477d22b80a8d07c7d0a3f41e)

These results suggest that the isolation and living conditions in Eyam lead to a higher transmissibility of the disease.
Furthermore, a life expectancy with plague over one week suggests that this epidemic was a bubonic plague rather
than a pneumonic plague that rather killed in one or two days.

[1]: http://www.plosone.org/article/info:doi/10.1371/journal.pone.0008401    "Validation of Inverse Seasonal Peak Mortality in Medieval Plagues, Including the Black Death, in Comparison to Modern Yersinia pestis-Variant Diseases"
[2]: http://en.wikipedia.org/wiki/William_Mompesson   "History of Eyam"
