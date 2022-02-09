<img src="https://user-images.githubusercontent.com/42075039/153235642-c290fb88-067b-4259-9587-c8a755dff387.png" width="400" height="500">

# Israel's groundwater quality in water drillings

This is an exploratory analysis of Israel's groundwater quality in drillings around the country published by the government database service.

### Background:

- The database hold records for the last 9 years (2012-2020).
- There are over 3,800 groundwater drillings used for production drinking water and for monitoring purposes.
- Water pollutants are divided into five main categories: chloride, organic, fuel, industrial and pesticides. Within each group there are several chemical pollutants.
- Along with the main database file, two additional supplementary files were used for data enrichment.

### The goal:
Examine the pollutants levels and their distribution around the country and try to identify patterns.
## Data source:
National government database:
 - https://data.gov.il/dataset
## EDA process:
csv file with 41,740 records
- Individual pollutants were grouped into five main categories.
- Original pollutants measurements were converted  log scale to assist with comparison and graph plotting’s.
- We can see that natural chemicals such has chloride and organic compounds (such as nitrogen) have normal distribution in nature. Whereas other pollutants families which are influenced by men actions, are not normally distributed.
<img src="https://user-images.githubusercontent.com/42075039/153230115-09897eed-3140-4d03-8120-3e27e64f27b1.png" width="800">

- Most measurements are zeros (74%) and the rest of the measurements are widely distributed.
- Most of the measurements are below the standard limit, but when there are exceedances (6.7%) then they are very high.
<img src="https://user-images.githubusercontent.com/42075039/153230765-9bcb7606-95be-429c-9c50-010e62bad89d.png" width="800">

- We see strong correlation between the follwoing parameters:
(ATAR,SIMZ), (BENZ,ETBN), (BENZ,MTBE), (BENZ,TOLU), (BENZ,XYLE), (CDCE,CHLF),(CDCE,DCEY), (CDCE,TCEY), (CDCE,TECE), (CHLF,DCEY), (DCEY,TCEY), (ETBN,MTBE),(ETBN,TOLU), (ETBN,XYLE), (MTBE,TOLU), (MTBE,XYLE), (TCEY,TECE), (TOLU,XYLE)

- After all the analysis done up until now, I found the following: 74% of measurements are zeros, 19% are above 0 and bellow 100 (standard limit) and only 7% are above the standard.
- This information may lead us to try another analysis approach which is called EVA (Extreme value analysis - Values occurring at the tails of a probability distribution). In this analysis we try to assess and predict the future by looking only at the extreme values. We divide our data into 'blocks' and decide on a threshold for the extrema values.

### Analysis of main pollutants groups versus main country area
- Out of all the industrial areas in the country, only 20 sites are continuaslly being monitored for pollutants in underground water, thru special monitor drillings.
<img src="https://user-images.githubusercontent.com/42075039/153233903-92461e71-e7e7-4a8c-8ee2-75c4bdf2d665.png" width="400" height="500">

 - The coast area is the one area which is significantly affected by fuel pollutants in groundwater.
 - Industrial pollutants are present in all  areas of the country, but with big concentration in the ‘coast’ and ‘yarkon’ areas.
 - Chloride and organic pollutants are present in all areas of country.
 - Most of the measurements do not exceed above the standard limit.
<img src="https://user-images.githubusercontent.com/42075039/153234222-41c7fe0b-a3a6-41b7-a6c0-6c8a37e01afc.png" height="300" width="800">
<img src="https://user-images.githubusercontent.com/42075039/153234244-0b50c32a-bfd5-4a21-a97a-b9e2ad62093b.png" height="300" width="800">
<img src="https://user-images.githubusercontent.com/42075039/153234617-adc27b7f-2683-4bc1-ac0a-b689984f0a39.png" height="300" width="800">

### Analysis based of geological aquifer layers
<img src="https://user-images.githubusercontent.com/42075039/153234841-bbaa698e-fee4-4ca0-b3d7-183ad2daa0bb.png" height="500" width="500">

- 78% of groundwater drillings are being made into the second and third geo layers (Pleistocene, Neogene).
<img src="https://user-images.githubusercontent.com/42075039/153234946-35b71bb0-9b90-4a92-9565-e5f1dca60bb2.png" width="600">
<img src="https://user-images.githubusercontent.com/42075039/153235132-da85b93e-8d0e-4f0f-b8fa-d7242030a2c1.png" width="600">

## Conclusions:
 - We find a relation between the 'coast' area which is only being drilled to the second geo layer (Pleistocene), to high level of fuel pollutants in production water drillings. This is supported by the fact that we do see high levels of fuel pollutants all over the country areas in monitoring drills.
 - Most measurements with high level pollutants (Industrial and Fuel) can be found in the second and third geo layers (Pleistocene, Neogene).
 - Although we find high levels of contaminations under Fuel and Industrial facilities, their impact on nearby production water drillings contamination levels, is relatively low.
