---
layout: page
title: "FAQ"
permalink: /faq/
---
## Table of Contents ##
1. [How can I download the data](#T1)?

2. [I’m trying to open the data in excel, and it is too large or too big. What can I do?](#T2)

3. [How can I get SafeGraph Geometry data -- it is not in the s3://sg-c19-response bucket?](#T3)

4. [Why is the schema different for Social Distancing Metrics for the dates 2020-01-01 through 2020-05-09 compared to before and after?](#T4)

5. [I want to reproduce SafeGraph’s Patterns foot-traffic and Re-opening dashboards. Can I download this data directly? If not, how can I reproduce these charts?](#T5)

6. [I want to reproduce SafeGraph’s Social Distancing Shelter-in-place Stay-at-home dashboard. Can I download this data directly? If not, how can I reproduce these charts?](#T6)

7. [I am publishing using SafeGraph data. How should I cite or attribute SafeGraph?](#T7)

8. [I am publishing using SafeGraph data. Is it OK for me to make the data publicly available so that other researchers can reproduce my research?](#T8)

9. [How can I join together (connect, crosswalk, link) data from CBG (census block group), zip codes / postal codes, census tracts, states, counties, or other SafeGraph POI places data?](#T9)

10. [I see an anomaly, outlier, inconsistency, or unexpected value in the data. What should I do?
The data is broken up into many files. How can I combine all the data into one file?](#T10)

11. [The data is broken up into many files. How can I combine all the data into one file?](#T11)

12. [What is a geohash?](#T12)

13. [What information is available about the SafeGraph data sample / panel? Is it representative or does it have biases?](#T13)

14. [The dataset (sample, panel) changes month to month and week to week. How do I account for this in my longitudinal analysis?](#T14)

---

### <a name="T1"/> How can I download the data? ###
- The primary recommendation is to download the data from AWS s3 using the aws-cli. [This spreadsheet](https://docs.google.com/spreadsheets/d/1UNWvPzkUTTlXBZ6M6iGhM_7sr8h-MxsZdE7iOszkAmk/edit?usp=sharing) lists all of the data available and these are the instructions for [downloading using the AWS](https://safegraphcovid19.slack.com/archives/C0109NPA543/p1585177965017700).
  - If you have questions, ask in [#aws-troubleshooting](https://safegraphcovid19.slack.com/archives/C0114D7SJCF/p1590522731391100)
- If you want access to bulk data but are not comfortable with the AWS-CLI or terminal, you can consider using [CloudBerry Explorer](https://safegraphcovid19.slack.com/archives/C0114D7SJCF/p1590522731391100), a free 3rd-party software program to download data from s3. Here are [instructions for using CloudBerry Explorer](https://docs.google.com/document/d/1R-EvZEWPATwH67hXyrczAK16dpCoJnOuMm4WeXUuQFI/edit?usp=sharing). 
  - If you have questions, ask in [#aws-troubleshooting](https://safegraphcovid19.slack.com/archives/C0114D7SJCF/p1590522731391100)
- If you only need a small cut of data, for example, only a specific geography or a specific time range, you can filter and download the data using one of the Consortium Partner Applications: 
  - [Unfolded](https://safegraphcovid19.slack.com/archives/C0115PHMGM6/p1590009745120200?thread_ts=1589999350.116900&cid=C0115PHMGM6)  -- questions @Sina [Unfolded]  
  - [Rill Data](https://safegraphcovid19.slack.com/archives/C0115PHMGM6/p1590010873123300)  -- questions contact @Mike Driscoll (Rill Data)  

### <a name="T2"/> I’m trying to open the data in excel, and it is too large or too big. What can I do? ###
- Check out [this link on Slack](https://safegraphcovid19.slack.com/archives/C0109NPA543/p1588201121330700)
- [How to open really large CSV files](https://www.csvexplorer.com/blog/open-big-csv/)


### <a name="T3"/> How can I get SafeGraph Geometry data -- it is not in the s3://sg-c19-response bucket? ###
- SafeGraph does not make Geometry available by default to members of the Consortium. 
- If you want SafeGraph Geometry data in order to calculate square-footage (area) of POI or for access to `polygon_class` or `is_synthetic` columns, this is available via the **Core Places Geometry Supplement (POI Area)** file. 
-  If your research requires access to additional columns, then you should download a sample of the Geometry data at SafeGraph data bar using the coupon code to confirm that Geometry data actually will help your use case. Once confirmed, please contact SafeGraph explaining your research needs, and providing the email you used to create your account on shop.safegraph.com, and we will try to enable you.

### <a name="T4"/> Why is the schema different for Social Distancing Metrics for the dates 2020-01-01 through 2020-05-09 compared to before and after? ###
Check out these links for more context and discussion about this via Slack:
  - [Social Distancing Metrics Announcement](https://safegraphcovid19.slack.com/archives/C0109NPA543/p1589320027227700)

### <a name="T5"/> I want to reproduce SafeGraph’s Patterns [foot-traffic](https://www.safegraph.com/dashboard/covid19-commerce-patterns) and [Re-opening dashboards](https://www.safegraph.com/dashboard/reopening-the-economy-foot-traffic?s=IA&d=04-26-2020&i=all). Can I download this data directly? If not, how can I reproduce these charts? ###
- We don't provide this data directly, but we have detailed documentation for you to reproduce these dashboards using the [Patterns](https://docs.safegraph.com/docs/places-schema#section-patterns) data.
- Here is detailed [documentation to reproduce the Patterns dashboards](https://docs.google.com/document/d/1lWodAzENz6rMlcFdPi6Y_B4M_ruCyXgeYoC8k9yY2eI/edit?usp=sharing). 
- See here for what [NAICS codes are being used](https://safegraphcovid19.slack.com/archives/C0109NPA543/p1590096693090000?thread_ts=1590096024.088700&cid=C0109NPA543). 
- Discussion: [from 2020-05-21](https://safegraphcovid19.slack.com/archives/C0109NPA543/p1590096024088700)

### <a name="T6"/> I want to reproduce SafeGraph’s [Social Distancing Shelter-in-place Stay-at-home](https://www.safegraph.com/dashboard/covid19-shelter-in-place) dashboard. Can I download this data directly? If not, how can I reproduce these charts? ###
- We don't provide this data directly, but we have detailed documentation for you to reproduce these dashboards using the Social Distancing Metrics data available here.
- Here is [detailed documentation](https://docs.google.com/document/d/1k_9LGQn95P5gHsSeuBdzgtEWGGCmzXdcOkcphWi0Cas/edit?usp=sharing) to reproduce the Shelter-in-Place dashboards and an appendix on [Bayesian Hierarchical Models](https://docs.google.com/document/d/1qAXl5iHJZCuyIPnawMHa6WoKULhsx404flTAGq0bStA/edit?usp=sharing). 

### <a name="T7"/> I am publishing using SafeGraph data. How should I cite or attribute SafeGraph? ###

- Add: "SafeGraph, a data company that aggregates anonymized location data from numerous applications in order to provide insights about physical places. To enhance privacy, SafeGraph excludes census block group information if fewer than five devices visited an establishment in a month from a given census block group."

- [More Context / Guidelines](https://safegraphcovid19.slack.com/archives/C0109NPA543/p1585946233411800)

- Discussion: From [2020-5-21](https://safegraphcovid19.slack.com/archives/C0109NPA543/p1590101512094800)

### <a name="T8"/> I am publishing using SafeGraph data. Is it OK for me to make the data publicly available so that other researchers can reproduce my research? ###
- [More Context / Guidelines](https://safegraphcovid19.slack.com/archives/C0109NPA543/p1585946233411800)
- It is against our terms of service and the data evaluation agreement to re-share raw SafeGraph data. It is OK to share aggregated and derived data, and to include data in chart and visual forms. 
- If you need to link out to the datasets, please provide links to our documentation for whichever dataset you are referencing and refer people to SafeGraph where we can distribute the data to them directly. 


### <a name="T9"/> How can I join together (connect, crosswalk, link) data from CBG (census block group), zip codes / postal codes, census tracts, states, counties, or other SafeGraph POI places data? ###
- How to Join X to Y. [Free resources to connect together IDs, boundaries, and indexes from disparate systems](https://docs.google.com/spreadsheets/d/14xMfW9xAXZLWuNcrSzxL16ddve0HAQ21zh99RAOjpsM/edit?usp=sharing)

### <a name="T10"/> I see an anomaly, outlier, inconsistency, or unexpected value in the data. What should I do? ###
- First, check the list of Known Data Issues on the eponymous tab of the [Data Products spreadsheet](https://docs.google.com/spreadsheets/d/1UNWvPzkUTTlXBZ6M6iGhM_7sr8h-MxsZdE7iOszkAmk/edit?usp=sharing). Others may have already reported.
- If it is not already reported, then please report your observation in [#safegraphdata](https://safegraphcovid19.slack.com/archives/C0109NPA543)  . Please include enough details for our team to reproduce (e.g., what specific Data products (Weekly Patterns? Social Distancing Metrics?), files/dates and column names). If you can provide a visualization to indicate the issue, that is extra helpful. 
- We will investigate and try to provide an explanation and possibly a correction. 

### <a name="T11"/> The data is broken up into many files. How can I combine all the data into one file? ###
- The data is broken up into many files because the data is large. 
- Working in python? Please see this link [HERE](https://safegraphcovid19.slack.com/archives/C010W1T8NF2/p1588295353019300?thread_ts=1587768194.419600&cid=C010W1T8NF2) and join the [python_troubleshooting](https://safegraphcovid19.slack.com/archives/C014FK2QWNL) channel for more help.
- Working in R? Please join the [r-troubleshooting](https://safegraphcovid19.slack.com/archives/C013B8TSETG) Slack channel for help. 
- Working in Excel? Please see [I’m trying to open the data in excel, and it is too large or too big. What can I do?](#T2).

### <a name="T12"/> What is a Geohash? ###
- [Wikipedia Link](https://en.wikipedia.org/wiki/Geohash)
- If you just want to build intuition, we recommend playing with these tools:  
  - [geohash.gofreerange.com](http://geohash.gofreerange.com/)
  - [www.movable-type.co.uk](https://www.movable-type.co.uk/scripts/geohash.html)
- Discussion: 
  - [From Slack](https://safegraphcovid19.slack.com/archives/C0109NPA543/p1587590325030500?thread_ts=1587172661.363500&cid=C0109NPA543)

### <a name="T13"/> What information is available about the SafeGraph data sample / panel? Is it representative or does it have biases? ###
- SafeGraph publishes several files to summarize the composition of the panel for transparency about panel composition and consistency. 
  - [home_panel_summary.csv](https://docs.safegraph.com/docs/places-schema#section-home-location-distributions-by-state-census-block-group)
  - [visit_panel_summary.csv](https://docs.safegraph.com/docs/places-schema#section-number-of-visits-visitors-by-state)
  - [normalization_stats.csv](https://docs.safegraph.com/docs/places-schema#section-normalization-stats-new)
- [What about Bias in SafeGraph Dataset](https://www.safegraph.com/blog/what-about-bias-in-the-safegraph-dataset)
- [Data Science Sources] (https://docs.safegraph.com/docs/data-science-resources)

### <a name="T14"/> The dataset (sample, panel) changes month to month and week to week. How do I account for this in my longitudinal analysis? ###

- SafeGraph publishes several files to summarize the composition of the panel for transparency about panel composition and consistency over time. 
  - [home_panel_summary.csv](https://docs.safegraph.com/docs/places-schema#section-home-location-distributions-by-state-census-block-group)
  - [visit_panel_summary.csv](https://docs.safegraph.com/docs/places-schema#section-number-of-visits-visitors-by-state)
  - [normalization_stats.csv](https://docs.safegraph.com/docs/places-schema#section-normalization-stats-new)
- See also [Panel Normalization for Longitudinal Analysis, Sampling Bias Corrections and Extrapolation](https://docs.safegraph.com/docs/data-science-resources). 

*FAQ content from Ryan Squire & Jack Lindsay's guides*

