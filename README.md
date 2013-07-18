plague-UK-1665
==============

The analysis of historic and recent records of plague epidemics have grought into relief 
surprising discrepancies between between the characteristics of past and present epidemics that we had
so far been attributing to plague. For example, [Mark Welford and Brian Bossak][1] have shown that while
current laboratory-confirmed casesgenerally occur between November and April, Medieval Black Death epidemics
recurrently burst between April and October. Have we been wrongly attributing the Black Death epidemics to the
bubonic and pneumonic plagues? This question remains open, and we are simply going to illustrate here how mechanistic
models could be used to provide further insight into the characteristics of present and historic epidemics. 


We will be looking at two time series of 1665 epidemics in the UK, each indicating the monthly number of deaths
caused by plague in London
and Eyam. Contrasting these two cases is not only interesting due to the population size difference between London 
and Eyam, that had respectively 460000 and 350 inhabitants at the beginning of the epidemics, but also due to the
[peculiar story of the city of Eyam][2]. As some villagers started to die from plague, the clergyman William Monpesson decided
to isolate the village in order to protect the neighbouring cities of Northern 
England. During one year, Eyam lived in quarantine. Food was cautiously supplied so that villagers did not starve.
Yet, at the end of the epidemic 250 people had died. 


This story sheds a particular light on the following time series that can be found
in the *Bills of Mortality*.  Since 1932, these records had been filled by English doctors who to monitor the deaths
due to tuberculosis, small pox, measles, French pox, and plague:

![data](https://raw.github.com/JDureau/plague-UK-1665/master/images/data.png?login=JDureau&token=c5b1e3d648591265b128978f10a0bcee)


To analyse this dataset we use a simple SI model, meaning the individuals are either infected with plague or 
susceptible to become infected.
Seasonal forcing is introduced, which timing and amplitude are being estimated. At last, we make no assumption
on the type of plague at stake, allowing the life expectancy after infection to lie between one and seven days
(respectively corresponding to pneumonic and bubonic plague).  Due to the inherent uncertainty
in data collection, observational noise needs to be accounted for when modeling the dynamic of these epidemics
as well as demographic stochasticity. The resulting estimates of the transmission potential of plague in each city, as
well as life expectancy with plague, are the following:

![data](https://raw.github.com/JDureau/plague-UK-1665/master/images/post.png?login=JDureau&token=cf7c103e477d22b80a8d07c7d0a3f41e)


These results provide information that could not have been inferred from straight observation of the time series of
deaths in each city.
First, they suggest that the isolation and living conditions in Eyam lead to a higher transmissibility of the
disease. Furthermore, life expectancy after infection appears to be close to one week, suggesting that this epidemic
was a bubonic plague rather than a pneumonic plague.


For the sake of transparency, and to foster further explorations of this problem and the data provided 
by  [Mark Welford and Brian Bossak][1], this repository provides the means to easily reproduce the presented results. 
It relies on the [library of inference methods][4] developed in collaboration with Sébastien Ballesteros as part
the the [PLOM.IO project][3].


Reproducing the results:
------------------------

Data is contained in the *data* folder, in the csv format. Additionally, the folder SI_seas contains json files that 
define a model and link it to the data, following the [PLOM.IO grammar][5]. To generate the code and play with the
model yourself, simply [install the package][6], and compile the model with:

    plom build -t map.json --local

The joint posterior density of parameters can be explored with:

    plom pipe map.json | ./pmcmc --full -J 2000 -N 8 -a 0.98 -M 20000
    
Which will create a trace_0.csv file.

[1]: http://www.plosone.org/article/info:doi/10.1371/journal.pone.0008401    "Validation of Inverse Seasonal Peak Mortality in Medieval Plagues, Including the Black Death, in Comparison to Modern Yersinia pestis-Variant Diseases"
[2]: http://en.wikipedia.org/wiki/William_Mompesson   "History of Eyam"
[3]: http://plom.io/ "PLOM.IO"
[4]: https://github.com/plom-io/plom-pipe "plom-pipe"
[5]: http://plom.io/cli/grammar "PLOM.IO grammar"
[6]: http://plom.io/cli "workflow"

