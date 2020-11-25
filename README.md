# etl_project
Extraction: We used two different sources to extract our data. The first source where we retrieved data from wa the US census american community survey using five year estiments. The data that our group retrieved from that website was intially formated as JSONs. Our group's other data source was the Chicago Data Portal, where the information was formated as csv files.
Transformation: For the censusa data, responses were compiled into a single dataframe and unneeded data was removed. The following 
columns were used in the transformation:

    GEO_ID - ID for geographic region
    B15003_001E - Total population
    B15003_002E - Total with no schooling completed
    B15003_003E - Total with nursery school as highest educational attainment
    B15003_004E - Total with kindergarten as highest educational attainment
    B15003_005E - Total with 1st grade as highest educational attainment
    B15003_006E - Total with 2nd grade as highest educational attainment
    B15003_007E - Total with 3rd grade as highest educational attainment
    B15003_008E - Total with 4th grade as highest educational attainment
    B15003_009E - Total with 5th grade as highest educational attainment
    B15003_010E - Total with 6th grade as highest educational attainment
    B15003_011E - Total with 7th grade as highest educational attainment
    B15003_012E - Total with 8th grade as highest educational attainment
    B15003_013E - Total with 9th grade as highest educational attainment
    B15003_014E - Total with 10th grade as highest educational attainment
    B15003_015E - Total with 11th grade as highest educational attainment
    B15003_016E - Total with 12th grade but no diplomma as highest educational attainment
    B15003_017E - Total with high school diploma as highest educational attainment
    B15003_018E - Total with GED or alternative as highest educational attainment
    B15003_019E - Total with Some college, less than 1 year as highest educational attainment
    B15003_020E - Total with Some college, 1 or more years, no degree as highest educational attainment
    B15003_021E - Total with Associates degree as highest educational attainment
    B15003_022E - Total with Bachelor's degree as highest educational attainment
    B15003_023E - Total with Master's degree as highest educational attainment
    B15003_024E - Total with Professional school degree as highest educational attainment
    B15003_025E - Total with Doctorate degree as highest educational attainment

Attainment levels were aggregated into broader categories (i.e. any amount of college attainment 
without a degree was combined into 'Some College'). Columns were renamed from their census variable code to more 
descriptive titles to improve readability. Finally, percent of total population was calculated for each aggregated attainment level. 
For the business licenses dataset extracted from City of Chicago data portal the data was transformed using Python and Jupiter Notebook. Unneeded data was removed from the data and left us with the following columns that were used in the transformation: 
Legal Name - Zip Code - License Description - Date Issued
Load: It was decided that the data would be put into SQL. The reason why SQL was chosen was becaue the data sets would be merged on a single coloumn, joining on zipcode. As such, SQL seemed like the best choice for doing huge joins between datasets.
outliers and next steps: On the census side of the data, o'hare airport has no data. for buisness liscenses, some were recorded to have registered not in the city of chicago or even the united states. Next steps would be looking for correlation between educational attainment and where licenses are registered. 