# EU Calc

This jupyter notebook shows how data from the EUCalc project is converted into using it for a Suffiency Quantification, comparing it to other studies.

## Data Source
We use data from the __bitbucket__ repository of EUcalc and Data downloaded from the EUcalc Website directly. This is needed because some main comparison parameters can be calculated using the data from the repository, for others we need the data from the Website. As scenario we use __Life__, as it is the one with the most ambitious goals.

The data from the bitbucket is stored in the folder __input/_eu_calc_rep_data__ and the data from the website in the folder __input/country_data__. In the repo data we have csv-files per category (e.g. food) and with different prefixes. Hereby the prefix _ots_ stands for historical data and _fts_ for scenario data. 

## Data processing
Then in the scenario csv-files we have a column for _year, country, lever_ and each _parameter_. Lever hereby indicates thes ambitions, so a high lever indicates a high change in behaviours. As stated before we used the _Life_ scenario, which has defined levers for each parameter. These levers are given in the __levers_life.json__ file. 

In the next step we have to process the __repo_data__. Therefore, we first define the needed parameters, then for each country we filter for the needed data with the levers given by the scenario. The scenario data has a value for lever 1 to 4, given as integers. But in the scenario we also have float numbers, e.g. 1.5. For these we have to calculate the scenario value using the upper and lower lever value and calculate the weighted mean. Then as output we have one file per country containing all parameters already with the correct levers, which are stored in the folder __output/country_data__. 

Now we use the output from before and the data from the Website to create a table similar to the __Scenario_Analysis__ Table used as data source for the study. In this step we also convert the units to the units used in the study. Then as final result we get the table __input_for_scenario_analysis__ which can be directly used for the Google Spreadsheet.


## Contributing
Frauke Wiese [1], 
Carina Zell-Ziegler [2, 3], 
Celia Burghardt [4], 
Yannick Kloos [4], 
Mirko Schäfer [4],

[1] Department of Sustainable Energy, Europa-Universität Flensburg, Auf dem Campus 1, Flensburg 24941, Germany
[2] Öko-Institut, Borkumstraße 2, 13189 Berlin, Germany
[3] Technical University of Berlin, Straße des 17. Juni 135, 10623 Berlin, Germany
[4] INATECH, University of Freiburg, Emmy-Noether-Str. 2, 79110 Freiburg, Germany

## Licensing
Shield: [![CC BY 4.0][cc-by-shield]][cc-by]

This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg
