# School District Analysis

## Overview of School District Analysis

The purpose of this project is to analyze a particular school district to look at factors that lead to better test scores in math and reading so that the school board can make informed decisions in the future. The data for this analysis was provided in csv files and was analyzed using Python, Pandas and Jupyter Notebook. Another factor that played in this analysis was when academic dishonesty was suspected for a particular grade at one of the high school, how did removing those numbers impact the school summary as well as the district summary. The results that the school board is interesting in are:

- How does removing the suspecious scores impact the district summary?
- How does removing the suspecious scores impact the school summary?
- How does replacing the suspecious scores impact the overall scores from Thomas High School?
- How does replacing the suspecious scores impact the following:
  - Math and Reading scores by grade
  - Scores by school spending
  - Scores by school size
  - Scores by school type

## Analysis of School District Data

In order to do this analysis, the csv files had to be examined and cleaned to remove all of the prefixes but keep the suffixes of the student names. The cleaned student data was then merged with the schools data to create a new data frame. This new combined dataframe was called school_data_complete_df. All of the data was checked for missing values and the types of the data was determined. The total number of students was counted using the count method counting by "Student ID". The total number of students was 39170. The total number of schools in this analysis is 15. The standard number for a passing test score is 70 or above. In order to figure out which students from each school is passing math and reading, all of the students with scores above 70 were put into new data frames and a third data frame was created with students passing both math and reading. The following numbers were then converted into percentages. Finally all of the this information was assembled into a new data frame and the top five performing schools and the bottom five performing schools were found. The performance of schools based on math and reading scores could then be examined by school type, school size and budget size.

### Removing Suspecious Data

When it was revealed that all of the test scores for the 9th graders at Thomas High School (THS) were suspected of academic dishonesty, the impact of these scores on Thomas High School's other scores and the rest of the district numbers were investigated. All of the 9th grade scores from Thomas High School were changed to NaN (not a number) so that they would not register as numbers and impact the rest of the measurements. All the 9th grade scores at Thomas High School were changed to NaNs using .loc() function to location and then change the scores. The number of students in the 9th grade could be counted using the .count() function and substracted from the total student count. Now that the 9th grade data from Thomas High School has been appropiate taken care of, all of the district summary metrics need to be recalculated.

## Results of School District Analysis

Now that the suspecious data has been nullified. The impact of this data on the rest of the outcomes calculated can be analyzed.

- How is the district summary impacted?
![Original District Summary](</Users/leahikenberry/Desktop/DU_DATA_Analytics/School_District_Analysis/Resources/Original_District_Sum.png>)
![Adjusted District Summary](</Users/leahikenberry/Desktop/DU_DATA_Analytics/School_District_Analysis/Resources/Adjusted_District_Sum.png>)
  - The top image is the original district summary before the Thomas 9th grade data was removed. The bottom image is the adjusted district summary after accounting for the Thomas High School data. From these summaries it is possible to see that accounting for the suspecious data from Thomas High School didn't change the district summary that much, only lowering the metrics by as much as 0.3%.

- How is the school summary impacted?
![Original School Summary](</Users/leahikenberry/Desktop/DU_DATA_Analysis/Resources/Original_THS_Sum.png>)
![Adjusted School Summary](</Users/leahikenberry/Desktop/DU_DATA_Analysis/Resources/Adjusted_THS_Sum.png>)
  - The top image is the original school summary that show cases all of the school's information. The bottom image is the adjusted school summary after Thomas High School was dealt with. These summaries show that removing the THS 9th grade scores dropped percentage of students passing math by 0.9%, students passing reading by 0.29% and students passing both math and reading (% overall passing) by 0.31%. These summaries were impacted more by removing the 9th grade THS data than the district summary.
- How does replacing the suspecious scores from Thomas High School impact the rest of the scores from Thomas High School?
![Original Top Five Schools](</Users/leahikenberry/Desktop/DU_DATA_Analysis/School_District_Analysis/Resources/Original_Top_Five_Schools.png>)
![Adjusted Top Five Schools](</Users/leahikenberry/Desktop/DU_DATA_Analysis/School_District_Analysis/Resources/Adjusted_Top_Five_Schools.png>)
  - The top image is the original ranking of the top five performcing schools based off of scores. The bottom image is after accounting for the 9th grade THS data. Thomas High School remains the second ranked school even after adjusting for the 9th grade data. There are only slight differences in the out come of the THS results as noted above. The following is looking at how other metrics were impacted by replacing the 9th grade data.
    - Math and Reading Scores by grade
      - The math and reading scores from THS were replaced with a NaN (not a number) meaning that they would impact the calculations of the rest of the THS numbers. As noted above, there are some slight differences in the outcomes of the reading and math scores after the 9th grade data was replaced with NaNs.
    - Scores by School Spending
    ![Original School Spending](</Users/Desktop/DU_DATA_Analysis/School_District_Analysis/Resources/Original_School_Spend.png>)
    ![Adjusted School Spending](</Users/Desktop/DU_DATA_Analysis/School_District_Analysis/Resources/Adjusted_School_Spend.png>)
      - As previously calculated, Thomas High School is in the $630-644 spending range and changing the 9th grade data did not change the amount spent by the school.
    - Scores by School Size
    ![Original School Size](</Users/Desktop/leahikenberry/DU_DATA_Analysis/School_District_Analysis/Resources/Original_School_Size.png>)
    ![Adjusted School Size](</Users/leahikenberry/Desktop/DU_DATA_Analysis/School_District_Analysis/Resources/Adjusted_School_Size.png>)
      - The top image is the original scores by school size and the bottom image is the adjusted scores by school size. Thomas High School falls into medium school category (1000-2000) by number of students and there are minimal differences between the original and adjusted summaries.
    - Scores by School Type
    ![Original School Type](</Users/leahikenberry/Desktop/DU_DATA_Analysis/School_District_Analysis/Resources/Original_School_Type.png>)
    ![Adjusted School Type](</Users/leahikenberry/Desktop/DU_DATA_Analysis/School_District_Analysis/Resources/Adjusted_School_Size.png>)
      - The top image is the original school type summary and the bottom is the adjusted school type summaryy. Thomas High School is a charter school and that was not impacted by adjusting the 9th grade scores.

### Summary of Results

The overall impact of removing the 9th grade math and reading scores from Thomas High School had a very minor impact on the overall results of this analysis. In regards to the which schools had better test scores, small to medium charter schools had higher test scores on average than larger district schools.

## Summary

Replacing the 9th grade test scores from Thomas High School with NaNs, did not greatly impact the outcome of the district summary. Part of the reason is that this is a very large sample size of over 39100 students and removing the test scores for 461 students does not greatly change the spread of data. The biggest difference was looking at the how the scores from Thomas High School was impact since the population of THS is under 2000 students and removing almost a fourth of the data will change the results. The biggest change of the overall percentage of students passing math and reading was 0.31% lower after removing the 9th grade data. Although statistical analysis was not used in this analysis, it is highly probable that removing the 9th grade data would not be statistically significant. However, it is always a good idea to rerun an analysis when new information comes to light about academic dishonesty even if it does not make a big difference overall.

## Resources

- Data Source: clean_students_complete.csv and schools_complete.csv
- Software: Python 3.6.1, Visual Studio Code 1.60.2, Jupyter Notebook
