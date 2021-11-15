# ANA261 - Modeling and Data Management with the New Model in SAP Analytics
## Description


With release 2021.QRC2, SAP Analytics Cloud introduced an entirely new model, imaginatively named [New Model](https://blogs.sap.com/2021/05/18/overview-of-the-new-model-in-sap-analytics-cloud/).  It introduces features such as measures, model-based calculations and brings the smart wrangler into the data management workflow.  This workshop consists of a series of exercises to familiarize you with the capability and workflows of SAP Analytics Cloud’s New Model.  

## Overview

In these exercises, you will take a tour of the New Model’s modeling basics and data management in SAP Analytics Cloud and build a simple model.  The data model is based on publicly available data from the United States National Park Service and contains visitation data to all units within the US National Park system from 1970 to 2020.

There are four exercises, which introduce you to the basics of creating a new model, loading data into it, troubleshooting and modifying existing load jobs and managing model-based calculated measures.

A note on the workflow – 
Currently (Q4 2021), there is no data first model creation workflow for the new model.  “Data first modeling” means that the model is created from data, either uploaded or from a data source and the model is built around the model.  The Dataset always uses a data first modeling workflow, and the classic account model can be created using a data first workflow.  In both cases, the model is built in wrangling.  Currently, if you create a model from data, an account model is created, not a new model.  

A structure first workflow means that the user first maps out how the model is structured and then loads the data into this structure later.



## Requirements


In this session, you have three SAP Analytics Cloud tenant options:  
* You may use the one provided to you for the session.  
* You may use your BTP trial tenant if you have provisioned one.
* You may use your own tenant and user if you have one.

The provided tenant is a preview tenant, but there is nothing in the exercises that requires a preview tenant.  If you are using your own setup, a development or production tenant is sufficient.

Tennant URL: [https://appdesign.eu10.sapanalytics.cloud/](https://appdesign.eu10.sapanalytics.cloud/)

User Credentials:
* Email: student01@sap.com to student50@sap.com
* Password: Welcome01

There is no guarantee that two people are not trying to use the same user at the same time. If you have a suitable tenant available, we recommend using that instead of the provided tenant simply to have your own personal user. As there are 50 users provisioned for this workshop on appdesign.eu10.sapanalytics.cloud, you can choose from one of fifty users and we hope to help avoid user collisions this way, but we still can't rule it out.

The data used in this workshop is a compilation of query data from the United States National Park service data query builder website. We’ll refer to this as the “National Parks Dataset”.  A cached copy is provided to you in the [data folder](https://github.com/SAP-samples/teched2021-ANA261/tree/main/exercises/data) as a convenient reference. Additionally, a copy has been uploaded as a public Google sheet.  In the exercises, we will configure our import job to draw directly from this public sheet.  

Data url: [https://docs.google.com/spreadsheets/d/1vi8fPg00o1ws-GptHCsMTdZkk_cQ3tz1hae6z7tQ0b4/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1vi8fPg00o1ws-GptHCsMTdZkk_cQ3tz1hae6z7tQ0b4/edit?usp=sharing)


## Exercises


There are four exercises in this workshop.

[Exercise 1](https://github.com/SAP-samples/teched2021-ANA261/tree/main/exercises/ex1) will explore the creation of the model data structure.  

[Exercise 2](https://github.com/SAP-samples/teched2021-ANA261/tree/main/exercises/ex2) will demonstrate loading data into your model

[Exercise 3](https://github.com/SAP-samples/teched2021-ANA261/tree/main/exercises/ex3) will explore modifying (re-wrangling) and re-running existing load jobs and modifying models with loaded fact data.

[Exercise 4](https://github.com/SAP-samples/teched2021-ANA261/tree/main/exercises/ex4) will demonstrate the creation of calculated measures in the model.  

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab..

## License

Copyright (c) 2020 SAP SE or an SAP affiliate company. All rights reserved. This file is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSE) file.
