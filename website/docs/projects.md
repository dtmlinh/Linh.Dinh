---
id: projects
title: Projects
---


## [Chicago PM2.5 Levels Comparison](https://github.com/dtmlinh/Air-Quality-Tool)

   A prototype tool which illustrates and compares 3 different PM 2.5 data sources, by day and neighborhood, in Chicago: ELPC community monitoring ([data](https://airqualitychicago.org/)), Environmental Protection Agency public air sample ([data](https://aqs.epa.gov/aqsweb/documents/data_api.html)), Purple Air self-reported ([data](https://www2.purpleair.com/)) \
   This tool aims to: \
    - illustrate the trends of PM 2.5 measurements in the Chicago area for 4 summers: 2017, 2018, 2019, 2020 \
    - identify days where the discrepancies (in terms of PM 2.5 levels) between AirQuality, EPA, and PurpleAir data are significant and locate the neighborhoods where these discrepancies might be coming from \
    - provide a more detailed view into specific neighborhoods, more specifically: \
      + locate blocks with much higher average PM 2.5 levels \
      + identify hours/time periods with much higher average PM 2.5 levels \
   Frameworks/tools/packages used: `Django`, Webscraping (`Selenium`), API Requests, `Plotly`, `Heroku` \
   *Access the tool [here](https://chicago-air-quality.herokuapp.com/).* \
   *And more detailed analysis results can be found [here](https://dtmlinh.github.io/Linh.Dinh/blog/2020/11/02/blog-post).* \
   ![](assets/air_quality_tool.gif)
    

## [Predicting housing prices in Chicago](https://github.com/ymericson/ml-project) 
   with Eric Son, Emily Zhang
   
   A machine learning model that predicts housing prices for 2021 (2 years ahead the latest available data) in Chicago, IL using neighborhood characteristics. \
   Our housing price data uses housing sales in 2013 - 2019 from the Cook County Assessor's Office, aggregated at the Census block group level. Our features include data on demographics, crime, distance to public transit, and more. The purpose of our model is to predict housing price trends in neighborhoods across Chicago, in order to help the city government better predict the areas where housing prices is expected to rise. More advance notice on housing price trends can help the city assess areas where affordability is expected to be more of an issue, so that they can focus resources for affordable housing. \
   Different sets of hyper parameters for each of the following models were tuned and evaluated: Simple Linear Regression, Ridge, Lasso, Elastic Net, Decision Tree Regressor, Random Forest Regressor, and Gradient Boosting Regressor. \
   *Access the full report [here](https://dtmlinh.github.io/Linh.Dinh/blog/2020/06/15/blog-post).* \
   ![](assets/Housing_Fig5.png)
    
    
## [Fatality rates of U.S. traffic accidents](https://github.com/dtmlinh/Traffic-Fatalities-HDFS)

   A project to look at the fatality rates of traffic accidents in the US and which factors might impact these rates. This project utitlizes several big data tools: AWS EMR cluster, `HDFS`, `Hive`, `Spark`, `Hbase`, etc. \ 
   The final output shows by State and Year: \
   - the fatality rate for serveral interesting conditions that might influence whether an accident is fatal or not: day vs. night time, at a junction, weather, etc. \
   - average number of minutes injured persons arrive at the hospital \
   - average number of hospitals within a 10 mile radius of the accident \
   - share of state spending on highway investments and health investments \
   ![](assets/Transportation-Analyses.gif) \
   *Additionally, here's a related [Shiny app](https://dtmlinh.shinyapps.io/car-crash-fatalities-exploration-tool/) ([Source Codes](https://github.com/dtmlinh/Car-Crash-Fatalities-Exploration-Tool)) that also looks at car crash fatalities in the U.S ([blog](https://dtmlinh.github.io/Linh.Dinh/blog/2014/04/10/blog-post)).*
   
   
## [Understanding Presidential Speeches and Executive Orders through Natural Language Processing](https://github.com/RobertoBarrosoLuque/ContentAnalysisPresidentialRhetoric) 
   with Lily Grier, Roberto Barroso Luque
   
   We used word frequency analysis, dependency parsing, sentiment analysis to show the idiosyncratic nature of presidential speeches. We used word embedding, topic modeling to understand legislative priorities of different presidents. \
   Frameworks/tools/packages used: NLP, word2vec, doc2vec \
   *Access the full report [here](https://github.com/RobertoBarrosoLuque/ContentAnalysisPresidentialRhetoric/blob/main/paper_folder/CCA_speeches.pdf).* \
   ![](assets/speeches.png)
    

## [Feature Extraction on Free-hand Sketches](https://github.com/dtmlinh/QuickDraw-Unsupervised-ML)
   with Xingyu Wang

   Wanting to see how neural network and unsupervised learning methods can aid abstract image classification, we extracted features using PCA, Self-Supervised, and Variational Autoencoder models on Google’s Quick, Draw! data, compared downstream classification results, and found that self-supervised learning techniques generally perform better. \
   Frameworks/tools/packages used: Pytorch, Tensorflow, CNN, RNN, VAE, Self-supervised Learning \
   *Access the full report [here](https://github.com/dtmlinh/QuickDraw-Unsupervised-ML/blob/main/Unsupervised_Final_Project_Paper.pdf).* \
   ![](assets/sketches.png)
    
    
## [Energy Consumption by State](https://github.com/dtmlinh/Energy-Search-Tool)
   with Eric Son, Emily Zhang

   A search engine of the energy consumption trends in U.S. states that outputs an energy source table and visual representations of consumption trends over time. \
   It uses a [Django](https://www.djangoproject.com/) web framework to display a search tool interface with data visualization option to look at a particular state or choose to compare with another state its energy consumption patterns and prices in 2017 (the latest year available), as well as historical time series of energy consumption by source. The state-level data for the project was imported from the [U.S. Energy Information Administration (EIA)](https://www.eia.gov/) website via web scraping and API. \
   Frameworks/tools/packages used: `Django`, Webscraping (`beautifulsoup4`), API Requests, `sqlite3`, `Heroku` \
   *Access the tool [here](https://us-energy-consumption.herokuapp.com/).* \
   ![](assets/state_energy_search.gif)
    

## [Food Inspections and Reviews](https://github.com/dtmlinh/Food-Inspections)
   with Matthew Mauer
   
   A web service that implements: \
   - POST requests to load and process data from food inspections and tweets for restaurants in the Chicago area, which then is stored in a `PostgreSQL` database using `pyscopg2`: \
        - food inspections: can be loaded individually from json format or loaded in bulk from csv format, checked for duplicative data, and handled appropriately \
        - tweets: are checked if they match any restaurants in the database, by name (matched by checking 1,2,3, and 4 gram words from tweet text and compare with restaurant name) or location (matched by comparing tweet lon/lat and restaurant lon/lat) \

   - GET requests to configure database/transaction settings, process loaded data, and return query results: \
        - database/transaction settings: \
            - configurable options: reset DB, reset transaction size, abort/rollback transactions, enable bulk-loading \
        - process loaded data: \
            - add/remove table indexes \
            - identify and link restaurants that are the same: record linkage from name, address, city, state, and zip with or without blocking and/or indexes \
        -  return query results: \
            - given a restaurant id, return all of its associated inspections \
            - given an inspection id, return the restaurant info (incl. all linked restaurants) \
            - given an inspection id, return all of its associated tweet keys \
   Frameworks/tools/packages used: `bottle`, `pyscopg2-binary` (or just `pyscopg2`), [`textdistance`](https://pypi.org/project/textdistance/), [`strsimpy`](https://pypi.org/project/strsimpy/) \

## Additional older projects 

   On my personal [Github](https://github.com/dtmlinh?tab=repositories). 
