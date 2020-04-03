# covid19model
Code for modelling estimated deaths and cases for COVID19. 

This repository has code for replication purposes. The bleeding edge code and advancements are done in a private repository. Ask report authors for any collaborations. 

# Installing dependencies

## Using Conda

An `environment.yml` file is provided and can be used to build a virtual
environment containing all model dependencies. Create the environment using:
```
conda env create -f environment.yml
```

Then activate the environment for use:
```
conda activate covid19model
```

## Using Docker

All dependencies for the model can be provided by building a [Docker][]
image. Please note that using this method separate instructions are required to
run the model - [see details](docker/).

[Docker]: https://www.docker.com/

## Other

If you wish to install packages into your native R environment or with a system
package manager please see `environment.yml` for a full list of dependencies.

# How to run the code

* Please enter the cloned directory and type 
`Rscript base.r base [ECDC RDS] [fatality CSV] [iterations] [warmups] [chains]` in terminal, e.g.
`Rscript base.r base data/COVID-19-up-to-date.rds data/weighted_fatality_0.2.csv 200 100 4`.
For comparability with report,
`Rscript base.r base data/COVID-19-up-to-date_original.rds data/weighted_fatality.csv 4000 2000 8`.
* The results are stored in two folders results and figures.
* Results has the stored stan fits and data used for plotting,
and also CSV data frames for each country.
* Figures have the images with daily cases, daily death and Rt for all countries.
