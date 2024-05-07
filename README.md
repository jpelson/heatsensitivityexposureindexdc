# Heat Sensitivity and Exposure Index For DC
A look into census tracts in DC that are sensitive and exposed to heat in DC as part of my final project for URSP 688Y

# Motivations
Rising temperatures and longer heat waves are creating urban heat islands, exacerbating environmental racism as some neighborhoods lack sufficient tree cover. This unequal distribution of green space and heat-absorbing surfaces puts residents at risk of heat-related illnesses. Data science can be a powerful tool to identify these vulnerable areas in Washington DC. By understanding the disparity, we can target interventions for maximum impact. This research aims to inform where planners and city officials should direct resources, focusing on both health and infrastructure. From a health and human services perspective, this could involve providing air conditioning assistance and conducting wellness checks on vulnerable populations. Infrastructure solutions might include establishing cooling centers and increasing green space through parks and tree planting initiatives.

# Central Question
How can data science be used to identify areas in Washington DC that are most vulnerable to heat due to unequal distribution of tree canopy and impervious surfaces, and where should interventions be  targeted to address this disparity?

# Approach
Using data from Open Data DC, the Python code created analyzes a geospatial dataset to identify areas in Washington DC that are vulnerable to heat due to either people -based health and socioeconomic factor or built environment factors.

First, the code mounts a Google Drive and imports necessary libraries for data manipulation and visualization using geopandas.

Next, the code loads a shapefile named "Heat_Sensitivity_Exposure_Index" which contains data on heat sensitivity and exposure for different census tracts in Washington DC. It then cleans and reformats the data for further analysis.

The code then calculates three indexes:
  Heat Sensitivity Index (HSI): This indicates how susceptible an area is to heat due to socioeconomic and demographic factors.
  Heat Exposure Index (HEI): This indicates how much heat an area is exposed to due to factors like lack of tree canopy, impervious surfaces, and ambient air temperature.
  Heat Sensitivity and Exposure Index (HSEI): This combines the above two factors to identify areas that are both heat sensitive and exposed.

For each index (HSI, HEI, HSEI), the code performs the following analysis:
  Sorts the data by the index in descending order.
  Filters out any rows with outliers.
  Identifies the top and bottom 10 census tracts based on the index values.
  Calculates the median value of the index.
  Creates a choropleth map to visualize the distribution of the index across different census tracts.

Finally, the code displays results including tables with tract IDs and index values, most and least vulnerable tracts, and median index values. It also generates maps to visualize the spatial distribution of these indexes.

# Results
Heat Sensitivity

Visualized on a map, dark purple areas represent census tracts with residents who are most sensitive to heat, gradually transitioning to lighter purples as sensitivity decreases. This sensitivity is determined by a combination of six social, economic, and demographic factors, along with three health conditions. These factors include race, age (both young children and older adults), income level, disability status, language barriers, and underlying health issues like asthma, heart disease, and obesity. It's important to note that three tracts with missing data were excluded from the analysis.
Interestingly, the median Heat Sensitivity Index (HSI) sits at 0.27, indicating that half of the city's census tracts fall within the bottom third of the HSI range. In other words, a significant portion of Washington DC has a high sensitivity to heat. This finding aligns somewhat with the city's demographics, suggesting a potential correlation.

Heat Exposure

Visualized on a map, dark orange areas represent census tracts with the highest Heat Exposure Index (HEI) levels, indicating the greatest exposure to heat. Lighter shades of orange depict areas with progressively lower HEI values. This HEI is determined by two key factors: ambient air temperature and the ability of the environment to retain heat. Heat retention is influenced by the amount of impervious surfaces like concrete and asphalt, and the lack of tree cover.
The median HEI of 0.67 reveals a concerning trend - over half (more than 103) of the tracts in DC face high heat exposure. This is further emphasized by the data clustering towards the upper half of the HEI range, suggesting a greater number of exposed areas. Interestingly, this finding aligns with DC's park and land use patterns. Rock Creek Park, with its abundant greenery, likely has a lower HEI (cooler area) compared to densely populated areas like Columbia Heights and downtown DC, which are likely depicted in darker orange on the map due to higher HEI (more exposed). This observed pattern is consistent with additional data on impervious surfaces and tree canopy cover.

Heat Sensitivity and Exposure

This map highlights census tracts in Washington DC that are most vulnerable to heat due to a combination of high heat sensitivity and exposure. Green areas represent tracts with lower vulnerability, meaning they are both less sensitive to heat and less exposed to it.  These areas often coincide with whiter, wealthier neighborhoods in northwest DC. Conversely, red areas represent tracts with the highest vulnerability, indicating high sensitivity to heat and high exposure. These areas frequently overlap with Columbia Heights and Brookland in northeast DC, which tend to have more Black and brown residents and a higher concentration of impervious surfaces like concrete and asphalt, along with less tree cover. The median value of 0.47 on this vulnerability index suggests that roughly half of the city experiences both high heat sensitivity and high heat exposure. This map serves as a valuable tool for urban planners, pinpointing areas where interventions to mitigate heat risks are most urgently needed.

# Implications

Heat vulnerability data empowers DC to fight heat risks. In the short term, it identifies at-risk populations for targeted outreach and allows for efficient resource allocation. Long-term, this data informs urban development with policies like green infrastructure or heat-resistant materials in vulnerable areas. Additionally, data-driven heat mitigation strategies can be implemented, leading to more effective interventions. Both short and long term, this data allows for targeted actions like tree planting, cooling centers, or heat-reflective pavements. By pinpointing vulnerable areas, improved emergency preparedness is also possible. Ultimately, focusing resources on these areas promotes a more equitable distribution of heat mitigation efforts, benefiting public health and well-being for all residents.

# Limitations and Weaknesses

While heat vulnerability maps offer valuable insights, it's important to acknowledge their limitations. The choice of factors included in the index can significantly impact the results. For instance, the current focus on heart disease, asthma, and obesity might miss other health risks. In addition, Obesity is a common but concerning health measure (one that is based on white men). BMI, a weight-to-height ratio, doesn't consider muscle mass or overall health habits. Additionally, crucial factors like access to transportation, air conditioning, and even air quality are often missing from the data. Imagine waiting for unreliable public transportation in stifling heat, or lacking the resources for air conditioning – these situations significantly elevate heat risk. Furthermore, relying on socioeconomic data by tract can perpetuate existing biases if not interpreted cautiously.  Even seemingly straightforward factors like tree canopy cover raise questions. Does the data consider canopy spread over the tract or just existing trees (that may be concentrated in parks and not in yards or along streets)?

Looking ahead, incorporating future temperature projections into the analysis would be immensely valuable.  Similarly, including a wider range of health data and accounting for population density (park area per capita) could provide a more nuanced picture.  Future studies could also explore access to green spaces beyond parks, social support networks, and even the effectiveness of existing cooling centers during extreme heat events.  By acknowledging these limitations and pursuing further research, heat vulnerability maps can evolve into even more powerful tools for safeguarding public health.

