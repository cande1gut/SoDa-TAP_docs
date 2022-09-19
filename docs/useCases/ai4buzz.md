---
template: overrides/main.html
title: AI4Buzz
---

# AI4Buzz

The purpose of this project is to analyze and visualize Twitter conversations around energy concepts. In this case and extensibily, the energy east pipeline cancellation (October 5th, 2017).

## Components

1. [CrateDB, Kafka, and JupyterLab]: [SoDa-TAP engine] and [statistical toolkit].
2. [Twitter client].
3. [APIs].
4. [Webpage and custom visualizations]: A main Wordpress site is externally hosted and each visualization is served through their own implemented [HTML template].
5. [External data parsing]: A notebook to do direct socket connection to CrateDB to fetch all data in a table.

    [CrateDB, Kafka, and JupyterLab]: https://www.sodatap.ml/en/latest/architecture/deployment/#own-environment
    [APIs]: https://github.com/cande1gut/SoDa-TAP/tree/main/APIs
    [Twitter Client]: https://github.com/cande1gut/SoDa-TAP/blob/main/clients/twitter.py
    [SoDa-TAP Engine]: https://github.com/cande1gut/SoDa-TAP/blob/main/notebooks/SoDa-TAP_Engine.ipynb
    [Statistical Toolkit]: https://github.com/cande1gut/SoDa-TAP/blob/main/notebooks/StatisticalToolkit.ipynb
    [Webpage and Custom Visualizations]: https://ai4buzz.ca/
    [HTML template]: https://github.com/cande1gut/cecn-visualizations/tree/main/socket/cecn
    [External data parsing]: https://github.com/cande1gut/SoDa-TAP/blob/main/notebooks/DataParsing.ipynb

## Deployment

All components are served as Docker containers in order to make things easier and automate most parts of the project. The previous mentioned components need to be deployed following their associated number:

1. CrateDB, Kafka, and JupyterLab need to be the first available containers deployed. The SoDa-TAP engine and the statistical toolkit notebooks need to be uploaded inside of the JupyterLab container to start processing/analysing data.
2. The Twitter client can be individually run or be used inside of the JupyterLab container in order to fetch the tweets that need to be analysed.
3. The APIs need to be deployed before the visualizations, so that the database can be accessed to request for the processed data.
4. The visualizations need to be deployed as a nginx container in order to serve all the HTML templates per energy type.

## Analyses

### Tweets

### Users
