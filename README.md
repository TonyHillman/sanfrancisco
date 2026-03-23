# San Francisco.
Data Mining course project based on the data sets from https://data.sfgov.org/ 

# SF Fire Incident Data Analysis

## Project Overview
A data mining workflow built in **KNIME Analytics Platform**.  
**GOAL:** Identify neighborhoods in San Francisco area that are at higher risk of dangerous fires than other neighborhoods.  
**DATASET:** San Francisco Fire Incident public data https://data.sfgov.org/Public-Safety/Fire-Incidents/wr8u-xric/about_data  

## Workflow
<img width="1767" height="847" alt="image" src="https://github.com/user-attachments/assets/e8c18858-45e6-4488-8d27-939da85eeb8b" />


### Key Nodes:
**CSV Reader** Import raw csv data  
**Math Formula** Used to sum Estimated Property Loss and Estimated Contents Loss to calculate Total Losses  
**Bar Chart** Visualization of neighborhoods sorted by Total Losses  
**Date & Time Difference** Used to calculate Response Time from Alarm DateTime and Arrival DateTime  
**K-Means** Used to cluster events by Response Time and other variables that correlate to the severity of the fire  
**Parallel Coordinates Plot** Visualization of clustered events  
**Bar Chart** Visualization of Neighborhoods sorted by their count of events in cluster 3  

## How to Run
1. Download and install [KNIME Analytics Platform](https://www.knime.com/).
2. Download the `.knwf` file from this repository.
3. In KNIME, go to `File > Import KNIME Workflow...` and select the file.
4. Ensure the data path in the "CSV Reader" node points to the included dataset.
5. Click "Execute All" (the double green arrow).

## Analysis of Results
Neighborhoods: Tenderloin, Mission, and Bayview Hunters Point experienced 2-5 times more total losses than the next highest neighborhood.

In cases of severe fires measured by relatively high numbers of alarms triggered and suppression personnel, response time is consistently low,
indicating that the dispatch and deployment process is operating with high efficiency to ensure large and dangerous fires are met rapidly with
sufficient resources.

Certain events that experienced significantly higher relative response times were grouped into cluster 3, indicating that there may be issues 
in the dispatch and deployment process to neighborhoods that frequently appear in this cluster. Neighborhoods were sorted by their number 
of events grouped into cluster 3 revealing the same three neighborhoods when sorted by Total Losses: Tenderloin, Mission, and Bayview Hunters Point.
This is far from a perfect method of analyzing this cluster as these neighborhoods may appear higher in count simply due to factors such as 
the size of the neighborhoods and population of people. There is room for future work in Analyses of neighborhoods experiencing significantly high average response times.

## Screenshots of Visuals

<img width="1822" height="840" alt="total_losses_chart" src="https://github.com/user-attachments/assets/11c4789a-5770-471a-8cb9-cf6d8df23190" />


<img width="1511" height="821" alt="image" src="https://github.com/user-attachments/assets/8d56f2ad-982c-4077-9aa8-244da4ff13f6" />


<img width="1822" height="840" alt="cluster_3_chart" src="https://github.com/user-attachments/assets/448a0ccf-a50b-4a71-a7fb-e27d47a774e8" />

