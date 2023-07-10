# ECON-Final-Project
Analyzing the Role of Income and Power Inequality on Groundwater Levels - Using R language and using the concepts of econometrics, data science and statistics, analyzed the role of income and power inequality on groundwater level using respective data sets and using various statistical tests.

### Introduction
Groundwater is a vital natural resource, and its
availability is crucial for sustaining agricultural and
industrial activities. However, groundwater
resources are under threat due to several factors,
including climate change, population growth, and
economic development. In this project, we aim to
investigate the role of income and power inequality
in influencing groundwater levels.
Income and power inequality are pressing issues in
today's world, and their effects are felt across
various domains, including economic growth, social
development, and environmental sustainability.
The project aims to contribute to the existing
literature by providing empirical evidence on the
relationship between income and power inequality
and groundwater levels.

### Libraries Used
dplyr
ggplot2
tidyverse
strucchange
sandwich
gap
lmtest
stargazer
data.table
fixest
magrittr

### Data Sets Descrption
- The repository includes the following datasets:

Groundwater level: Contains data on groundwater level.
Election Margin: Contains data on election margin.
Party Count: Contains data on the count of distinct parties.
Percent Women Elected: Contains data on the percentage of women elected
Telecom: Contains data on telecommunications.
Gini: Contains data on the Gini index.
Population Density: Contains population density data.
SDP: Contains state domestic product data

### Variables
- Groundwater Level: It is measured as the 
vertical distance in 
meters from the ground 
to the water.
- State Domestic Product: Measured as per capita 
net state domestic 
product in rupees.
- Gini Index: It is ratio that represent 
the income distribution.

### Base-Line Model
Ground.water.leveli,t = β0 + β1SDP(i,t) + β2SDP2(i,t) + β3SDP3(i,t) + β4Gini(i,t)

### Enhanced Model
year_state_GWLi,t = β0 + β1SDP(i,t) + β2SDP2(i,t) + β3SDP3(i,t) + β4StateGini(i,t) + β5party_count(i,t) + β6election_margin(i,t) + β7percent_women_elected(i,t) + β8rainfall(i,t) + β9population_density(i,t) + γ(i,t)

### New Regressors
- election_margin: The difference in no. of votes won by the 
winning party and the party that came second in State Lok 
Sabha election
- party_count: The number of effective parties competing in 
the state.
- percent_women_elected: The percentage on seats won by 
women in the state out of all available seats.
- rainfall: The total rainfall (in mm) received by the state in a 
given year.
- population_density: The number of people per sq km in a 
state of India.

### Conclusion
- Income inequality: Gini index is statistically significant and negatively correlated with the 
GWL. This suggests that higher the gini (income inequality), lower is the GWL. 
- Power Inequality: Election_margin and party_count are positively correlated with GWL, 
whereas percent_elected_women is negatively correlated. 
- Control Variables: Population_density is negatively correlated with groundwater level 
which means that the groundwater level reduces if the population of people per unit area 
in a state increases. Rainfall on the other hand is negatively correlated to the groundwater 
level which is contrary to what we expected. 
- Using BP test we got our p-value to be 1.31e-14 which means that our data was 
heteroskedastic. We fixed it using the FGLS method of weighted least squares after 
which we got our p value to be 0.4092.
- Since the distribution of Ground water level is highly right-skewed, we perform MLE 
estimation assuming a gamma distribution for the population. The coefficient estimates 
observed after this were similar to the OLS estimates with the exception of rainfall 
variable.
- We encountered structural break points across the state groups in the model. This 
suggests that the coefficients of estimations across the state groups vary significantly

