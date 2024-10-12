#Quiz Results Discrimination Analysis Report
Objective
This report presents an analysis of the quiz results from the dataset P4-ScoreData.csv. The primary goal was to calculate the Discrimination statistic for each question in the quiz, which evaluates how effectively each question differentiates between students with varying performance levels. The correlation between individual question scores and overall quiz performance was assessed to identify questions that may require review.

About the Dataset
The dataset P4-ScoreData.csv contains the results of a quiz taken by 15 students across 10 questions. Each student's score is recorded, and some students may have left questions unanswered, which are represented as missing values (NaN).

Key Features
Number of Students: 15
Number of Questions: 10
Data Features: Each row represents a student's score across various questions.
Methodology
Data Preparation:

Imported necessary libraries: Pandas and NumPy.
Loaded the dataset using pd.read_csv and filled missing values with zeros using df.fillna(0, inplace=True).
Set the 'Name' column as the index for easier data manipulation with df.set_index('Name', inplace=True).
Data Exploration:

Printed the number of students and questions.
Calculated the mean and standard deviation for each question using mean() and std() functions.
Total Score Calculation:

Added a new column 'Total' to compute each student's total quiz score using df.sum(axis=1).
Calculated the overall quiz mean and standard deviation from the 'Total' column.
Discrimination Statistic Calculation:

Created a new DataFrame for the first 10 question columns.
For each question, calculated:
The difference between student scores and the question mean, normalized by the question standard deviation.
The difference between total scores and the overall quiz mean, normalized by the overall standard deviation.
Multiplied the normalized differences to obtain the Discrimination statistic for each question.
Summed the results and divided by the number of students minus one to finalize the Discrimination statistics.
Alternative Calculation:

Used the Pandas corrwith function to compute the Pearson correlation coefficient as an alternative method for determining Discrimination statistics.
Results
Discrimination Statistics
The calculated Discrimination statistics for each question were as follows:

Question	Discrimination Statistic
Q1	0.782554
Q2	0.353454
Q3	0.694002
Q4	0.757120
Q5	-0.258207
Q6	0.855192
Q7	0.690915
Q8	0.759503
Q9	0.251805
Q10	0.789262
Observations
Question Requiring Review:
Question 5 has a Discrimination statistic of -0.258207, indicating that it may not effectively differentiate between high and low performers. Students who performed well overall did poorly on this question.
Alternative Calculation
The Discrimination statistics calculated using the corrwith function yielded the same results, confirming the accuracy of the initial calculations.

Interpretation of Results
a. Question Needing Review
Question 5 needs to be reviewed as it has a negative Discrimination statistic. This indicates that students who excelled in the overall quiz did not perform well on this question.
b. Consideration of Interpretation
A negative correlation does not necessarily imply that Question 5 is flawed. It could reflect external factors or unrelated variables affecting student performance on this specific question. Other aspects, such as question clarity, topic coverage, or student preparation, may contribute to the observed results.
Conclusion
The analysis of the quiz results has provided valuable insights into the performance of individual questions. The kind of Discrimination statistics will assist educators in identifying which questions may require modification or further review to enhance their effectiveness in assessing student knowledge. Future analyses could expand on these findings by exploring other metrics or incorporating qualitative feedback from students regarding their quiz experience.
