# Compressor Analytics Challenge and Data
## Launch Notebook
|          Platform         |                                                              Click Button To Launch                                                              |
|:-------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------:|
|        Google Colab       | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/aihack20/shell_challenge) |
| Standard Jupyter Notebook |                   [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/aihack20/shell_challenge/master)                  |
## Problem Statement 
### Situation:
We have a low pressure compressor (LPC, or just referred to as “asset”). The issue is that sometimes the compressor
“trips”
This is bad because:
- It's very unsafe for the engineers to be around an unstable compressor
- CO2 cost of downtime is huge
- It costs a lot of money to manually figure out the issue and fix it with new parts
### Mission:
Show us something interesting. We will give you a few ideas that we like/have experience with, but you can do
whatever you like.
### Where did the come from?
Multivariate timeseries from a low pressure compressor (LPC), recorded by a variety of sensors around the asset
|            |       Raw Dataset       |       Clean Dataset |
|------------|:-----------------------:|--------------------:|
| File size  |          570 Mb         |              444 Mb |
| Dimensions | 131,904 rows X 405 cols | 106,710 X 362 (+1)* |
- Originally interpolated to fit 10 minute intervals (before we received it)
- All data is from the same asset (possibly multiple but closely related machines)
- We’ve done some cleaning for/ you (recommended general cleaning, details next slides)
### What did we do to the data
#### Simplified:
Removed feature IDs – replaced with names (temperature, pressure, flow rate etc.)
Removed the timestamps (ordering is preserved)
#### Cleaned:
Removed all datapoints which correspond with the asset being shut down:
Temperature too low (below 80)
Exit pressure too high (above 58)
No smoothing at the gaps created, but we provide the original indexes (as another column), so you can find gaps and interpolate/smooth yourselves if you wish (we remove a 4 hour window on both sides around each gap created, to allow the machine to return to normal behaviour)
### Some Ideas
#### Interpretable anomaly detection
Can you classify/detect given anomalies well? (we provide a text file with some more info)
Can you provide causes for anomalous behaviour?
How do you assess how anomalous a particular value/event/timespan is?
#### Feature clustering and how this changes over time
Can you find out which features are more closely related than others?
How does this change over time, if at all?
What different metrics/spaces could you use for clustering?
### Time series forecasting
Can you accurately predict upcoming values/events*?
Can you find out how certain/uncertain you are about predictions?
What timescales/resolutions can you forecast at? 
### Digital twin/Compressor simulator
Can you create a (generative?) model that can simulate the asset and generate synthetic data (Digital twin)?
How can you ensure what the model generates is actually a timeseries?
What examples can you show of how the Digital twin is useful for understanding the asset? 
### Or anything else you think is interesting
It would be nice if it solves or gives more insight into the issues specified in the situation
It doesn't necessarily have to have a direct business application
We will be here to help out regardless and offer feedback on ideas (we are not involved in judging/assessment process)








