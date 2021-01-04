---
date: 2020-05-23
excerpt: "Visualization of COVID-19 cases across the globe"
header: ~
tags:
  - tableau
  - visualization
  - pre-processing
title: "COVID-19 Tracker"
---

COVID-19, the disease caused by the novel coronavirus, first hit China in December 2019. With the perpetuation of international travel as under normal circumstances, the disease steadily turned into a global pandemic infecting and claiming lives of millions.

Numerous tools have been built in order to inform researchers, public health authorities and the public about the outbreak as it unfolds. Such tools generate awareness among people and help in designing public health policies by providing information on the key metrics associated with COVID-19 - confirmed cases, active cases, deaths and recoveries.

The presented [COVID-19 Tracker] (https://public.tableau.com/profile/saumya.sinha1550#!/vizhome/COVID-19Tracker_15890027505320/GlobalView) provides a summary of the above-mentioned metrics; national breakdown and state-level breakdown, where available, of the metrics; and also the ability to sort nations based on the selected metric.

The data was sourced from Johns Hopkins Open Data, pre-processed on R and visualised on Tableau. The dashboard was **last refreshed on 22nd March 2020**.

Data pre-processing steps include -
1. Binding rows from different files into a single data frame
2. Renaming column headers
3. Removing whitespaces from State and Country
4. Renaming countries into a standard country name format
5. Standardizing the date format for LastUpdatedDate
6. Dealing with NA values

The data was then written to a new CSV file and fed into Tableau Desktop 2020 for visualisation. While bar charts provide a quick summary of the global numbers across the metrics, the map reports national numbers of the metric selected from the list with a colour scale; the darker a country is shaded, the higher the selected metric is on the numeric scale. 

At the time of last refresh of the dashboard, China held the top spot for total confirmed cases. On hovering over China, it was seen that over 90% of the cases were localised to a single province within the country. A tabular view of key metrics by country is driven by a dropdown to sort countries alphabetically or based on the selected metric. This option made it easy to see that at the time of last refresh Italy, only second to China in terms of confirmed cases, had seen the maximum number of deaths.