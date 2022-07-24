# School_District_Analysis

This project aims to extract the relevant data utilizing the student performance information for the 9th to 12th grade students, as well as the school budget, size and type data from the following High Schools:

1.	Bailey High School
2.	Cabrera High School
3.	Figueroa High School
4.	Ford High School
5.	Griffin High School
6.	Hernandez High School
7.	Holden High School
8.	Huang High School
9.	Johnson High School
10.	Pena High School
11.	Rodriguez High School
12.	Shelton High School
13.	Thomas High School
14.	Wilson High School
15.	Wright High School

The 9th grade Students from Thomas High School were involved in academic dishonesty by altering the grades for reading and math, thus a reasssessment for the individual, grade-level and school performance is required to determine the impact this action had on the performance metrics and school ranking.

## Overview of Project

![Previous_Results](/Images/Previous_THS_Final_Data.png)
*Previous Analysis Results*

Previously, this was the resulting information for Thomas High School analysis, which provided the average scores, passing rate, spending ranges and school student size. 

These calculation were made considering the 9th grade students whose grades are now reported as invalid.

After removing those grades from our dataset, and reassessing the dataset, the following results are obtained:

![Reassessed_Results](/Images/New_THS_Final_Data.png)
*New Analysis Results*

The Per Student Budget and Total Students are unnafected since, even if their grades were altered, we need to count the 9th grade students to have the real values for the Per Student Budget and the School size; these students however were not included in the Scores and % Passing calculations.

After dropping the 9th grade scores, Thomas High School's Average Math score drops by 0.06 and their Average Reading score increases by 0.05; the % Passing Math drops by 0.09% and the % Passing Reading 0.29%. The Overall Passing % decreases from 90.94% to 90.63%.

### Purpose

In order to make the proper budget allocation, as well as identifying trends and improvement areas in the school districts managed by the school board, its necessary to have the real information about how the 9th to 12th grade students are performing in the different schools.

Aspects such as budget per student; which is determined by the total population in a school and the alloted budget for said school. The performance per total population in a school and the school type (charter or district) are relevant to the school board since it highlights what's best for the students.

Since the 9th grade student scores for Thomas High School were altered, the board can't use the previous analysis as a reliable source for decision-making. 

Thomas High School is the second best performing school regarding the overall passing rate for both math and reading, where the minimum passing grade is 70 out of 100. Having altered the data of a high-performing school demands a more thorough investigation since it's unknown if their success could be attributed to altered scores.

## Analysis

The two datasets that were used for this project, below are the images that summarize the data contained in each:

![School_Data](/Images/Total_School_Data.png)
*School Dataset*

![Student_Data](/Images/Total_Student_Data.png)
*Student Dataset*

The Student Dataset that all Thomas High School 9th grade students had their grades replaced by NaNs; by using the following code:

'student_data_df.loc[(student_data_df["grade"] == "9th") & (student_data_df["school_name"] == "Thomas High School"), ["math_score"]] = np.nan'

'student_data_df.loc[(student_data_df["grade"] == "9th") & (student_data_df["school_name"] == "Thomas High School"), ["reading_score"]] = np.nan'

All the math and reading scores for the student data dataframe for 9th grade students from Thomas High School were changed into NaNs as shown in the next image:

![9th_Grade_NaNs](/Images/9th_Graders_NaN_Scores.png)
*Updated student scores*

The following ranges were used to calculate the budget per student:

![Spending_Ranges](/Images/Budget_Bins.png)
*Spending Ranges*

The following groups were used to group the schools according to their student count:

![Student_Count_Bins](/Images/Student_Count_Bins.png)
*Student Count Groups*

The calculation for Thomas High School passing percentages is done by substracting the population of their 9th grade students from their total student count. Below are included the tables that summarize the effect that considering the 9th grade students in the count used to calculated their passing percentage has:

![Thomas_High_School_with_NaNs](/Images/New_THS_Summary_With_NaNs.png)
*Thomas High School calculations without substracting the 9th graders from their total student count for calculation purposes*

![Thomas_High_School_without_NaNs](/Images/New_THS_Summary_Without_NaNs.png)
*Thomas High School calculations after substracting the 9th graders from their total student count for calculation purposes*

This analysis uses the passing percentages that are calculated by substracting the 9th grade student count.

### Results 

In this section, the comparison between the assessment done using the original student and school data, and the updated student and school data will be presented.

Thomas High School's 9th grade students amount to a total of 461 students; the total amount of 9th grade students in the dataset is 11408; which means that less than 5% of the 9th graders population were substracted from it. Thomas High School has a total of 1635 students, therefore 28% of their students are currently in 9th grade.

* District Summary Comparison

![New_District_Summary](/Images/New_District_Summary.png)
*Reassessment District Summary* 

![Previous_District_Summary](/Images/Previous_District_Summary.png)
*Previous District Summary*

After recalculating the average scores and their appropriate passing rates for the whole district, the effect that substracting the Thomas High School students is neglibile since they're only 461 out of the 39170 total students. 

The Average Math score dropped by 0.1, the Reading Score was not significantly affected. The percentage of students who passed math decreased by 0.2% while the percentage of students who passed reading dropped by 0.3%. The overall passing rate dropped by 0.1%.

* Math Scores per Grade Comparison

![New_Math_Scores_Per_Grade](/Images/New_Math_Scores.png)
*Reassessment Math Scores per Grade Summary*

![Previous_Math_Scores_Per_Grade](/Images/Previous_Math_Scores.png)
*Previous Math Scores per Grade Summary*

Since this calculation is done for each school and each grade, only the 9th graders score from Thomas High School were affected. Thomas High School previously had a score of 83.6, which meant it was positioned in the top 3 schools regarding math scores for 9th graders.

* Reading Scores per Grade Comparison

![New_Reading_Scores_Per_Grade](/Images/New_Reading_Scores.png)
*Reassessment Math Scores per Grade Summary*

![Previous_Reading_Scores_Per_Grade](/Images/Previous_Reading_Scores.png)
*Previous Math Scores per Grade Summary*

Since this calculation is done for each school and each grade, only the 9th graders score from Thomas High School were affected. Thomas High School previosuly had a score of 83.7, which was the 5th highest reading score among the 15 schools in this district.

* School Type Comparison

![New_School_Type_Summary](/Images/New_School_Type_Summary.png)
*Reassessed School Type Summary*

![Previous_School_Type_Summary](/Images/Previous_School_Type_Summary.png)
*Previous School Type Summary*

The unformatted tables were presented since the difference when rounding the numbers is less noticeable.

Thomas High School is a Charter type school, hence only the Charter row was affected. The average math and reading score both dropped by 0.01. The passing math percentage dropped by 0.01%  while the reading passing percentage dropped by 0.03%. The overall passing percentage dropped 0.04% compared to the original analysis. 

* School Student Size Comparison

![New_Student_Size_Comparison](/Images/New_Size_Summary.png)
*Reassessed performance by school student size*

![Previous_Student_Size_Comparison](/Images/Previous_Size_Summary.png)
*Previous performance by school student size*

The unformatted tables were presented since the difference when rounding the numbers is less noticeable.

Thomas High School is classified within the Medium sized schools (student count that goes from 1000 to 1999); small and large schools are not affected by this reassessment.

The average math score decreased by 0.01 and the average reading score increased by 0.01. The percentage of students that passed math drooped by 0.01%, the percentage that passed reading dropped by 0.06% while the percentage of students that passed both subjects dropped by 0.07%

* Spending per Student Comparison

![New_Spending_per_Student](/Images/New_Spending_Summary.png)
*Reassessed performance by spending per student

![Previous_Spending_per_Student](/Images/Previous_Spending_Summary.png)
*Previous performance by spending per student

The unformatted tables were presented since the difference when rounding the numbers is less noticeable.

Thomas High School falls in the $631-645 spending range; the other spending ranges are not affected by this reassessment.

The new calculations by leaving out the Thomas High School 9th grade students resulted in the following changes: the average math score dropped by 0.01, the average reading score increased by 0.01, the percentage of students that passed math decreased by 0.02%, the percentage of students that passed reading dropped by 0.08% and the overall passing rate dropped by 0.08%

* Top School Results Comparison

![New_Top_Schools](/Images/New_Top_Schools.png)
*New school ranking per overall passing rate*

![Previous_Top_Schools](/Images/Previous_Top_Schools.png)
*Previous school ranking per overall passing rate*

Both the current and previous reassessment show that Thomas High School holds the second place in overall passing rate; before the board reported that Thomas High School had modified their student's grades, they had an overall passing percentage of 90.94, however after removing the altered grades, their overall passing grade is now 90.63. Leaving them much closer to fall to either third or fourth place as in the overall passing percentage ranking

### Summary

After updating the student scores in the dataset, their effect in the overall district performance could be considered as negligiible since the thomas high school 9th grade students (461) are a negligible portion from the total student count (39170) and are not also a significant part of the total 9th grade student count (11408).

Regarding the district summary, the 9th grade students from Thomas High School are not substracted from the total student count. The total student count should include these students since part of the school's budget is also allocated to them; by removing them from the total student count then we'd obtain a fictional spending per student amount.

As mentioned previously, given the small size of the students whose grades were considered invalid, the values in our reassessment are not significantly different from those in the original assessment. 

The score differences in both math and reading are less than 0.01 points, and their effect in the percentage is 0.3% at maximum with the reading passing percentage, and 0.1% in both math and overall passing percentage

The modified 9th grader scores for Thomas High School were not randomly selected; as seen in the results, their effect when comparing the original and the reassessment is negligible, even the school ranking by overall passing percentage was not modified.