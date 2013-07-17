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
in agreement with Thomas Stanley to isolate the 


>In the summer of 1665, the village tailor received a parcel of material from his supplier in London. This parcel 
>contained the fleas that caused the plague. The tailor was dead from the plague within one week of receiving his
>parcel. By the end of September, five more villagers had died. Twenty three died in October.
>
> Some of the villagers suggested that they should flee the village for the nearby city of Sheffield. Mompesson 
> persuaded them not to do this as he feared that they would spread the plague into the north of England that had
> more or less escaped the worst of it. In fact, the village decided to cut itself off from the outside would. They
> effectively agreed to quarantine themselves even though it would mean death for many of them.
>
>The village was supplied with food by those who lived outside of the village. People brought supplies and left them
>at the parish stones that marked the start of Eyam. The villages left money in a water trough filled with vinegar to
>steralise the coins left in them. In this way, Eyam was not left to starve to death. Those who supplied the food did
>not come into contact with the villagers. 

> Eyam continued to be hit by the plague in 1666. The rector, Mompesson, had to bury his own family in the churchyard
> of Eyam. His wife died in August 1666. He decided to hold his services outside to reduce the chances of people 
> catching the disease."
>
> By November 1666, the plague was considered at an end. 260 out of 350 had died in the village but their sacrifice may 
> well have saved many thousands of lives in the north of England.
> 
> *quoted from [http://www.historylearningsite.co.uk/eyam_and_the_great_plague_o.htm][2]*


Although the dates do not match, this story sheds a particular light on the following time series that can be found
in the *Bills of Mortality*.  Since 1932, these records had been filled by English doctors who had been asked to 
identify the deaths due  tuberculosis, small pox, measles, French pox, and plague:

![data](https://raw.github.com/JDureau/plague-UK-1665/master/images/data.png?login=JDureau&token=c5b1e3d648591265b128978f10a0bcee)

These numbers were collected 
We use a simple SI model, meaning the individuals are either infected with plague or susceptible to become infected.
Seasonal forcing is introduced, which timing and amplitude are being estimated. At last, we consider that life
expectancy with plague is between 1 and 10 days. Due to the inherent uncertainty
in data collection, observational noise needs to be accounted for when modeling the dynamic of these epidemics.
In addition, we know that disease transmissions are a random process. At an agregated scale, this variability that 
is also called demographic stochasticity fades out. Nevertheless, it may be necessary to take it into account
in a small village as Eyam...


[1]: http://www.plosone.org/article/info:doi/10.1371/journal.pone.0008401    "Validation of Inverse Seasonal Peak Mortality in Medieval Plagues, Including the Black Death, in Comparison to Modern Yersinia pestis-Variant Diseases"
[2]: http://en.wikipedia.org/wiki/William_Mompesson   "History of Eyam"
