This README.txt file contains an overview of the different files used in computing the results for the paper titled

"Statistical Equity in Ohio Cross Country Competition"  
by Matt Kretchmar, Zhe Wang, and John Platt


--------------------------------------------------------------------------
DATABASE:
--------------------------------------------------------------------------
OH_XC.sql.gz
gzipped database containing the five years of post-season records from Ohio XC competition.
mysql engine was used


--------------------------------------------------------------------------
JUPYTER NOTEBOOKS:
--------------------------------------------------------------------------
1) MC_FREQ_SQL.ipynb
This notebook does the first part of the EXPECTED results calculations.  We query the DB in order to find the teams that participated in OH XC postseason during the five year period 2017-2021.
The data is stored as a series of 30 .csv files (see below).

2) MC_FREQ_ANALYSIS.ipynb
This notebook reads the csv files created above and then runs simulations (10,000 seasons worth) to create results.  The simulations use proportionality to create the results.  We record 22 different results for each team
Top 20 places in states
Regionals only
Districts only
Of the 10,000 seasons, we compute the number of times each team makes it to one of the above 22 categories.  

The results are stored in 30 .txt files. 

3) XC_Stat_Expected.ipynb
This notebook reads the 30 .txt files created above and then does the computation to create a table of expected results.   There are nine boxes:

		Smallest 25%     Middle 50%    Largest 25%
Districts:          X                X             X
Regionals:          X                X             X
States:             X                X             X 

Where the X's are all probabilities based on the counts from 10,000 seasons of simulation.

4) MC_Stat_Actual.ipynb
This notebook does the ACTUAL result counts.  It queries the DB and divides up the actual numbers for each team in the same 9-grid table as above.

We can then (separately) perform the computation of the Chi-Square test on the 6 experiments
(Division 1,2,3   x   Gender B,G)


--------------------------------------------------------------------------
DATAFILES:
--------------------------------------------------------------------------

We have 30 files that are .csv files.  They correspond to the 30 different experiments formed by
3 divisions (I, II, III)
2 genders ( B, G )
5 years (2017-2021)
They contain all the schools from the Ohio XC race database that competed post-season during this five year period.

We have 30 files that are .txt files.  The correspond to the same 30 different experiments above.  These .txt files contain counts of how each team finished in 10,000 different simulated seasons.  The simulation is carried out using proportionality.  These files allow us to compute EXPECTED counts for the 9-grid table.  

