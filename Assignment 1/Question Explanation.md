# Question 1
Write a function called proportion_of_education which returns the proportion of children in the dataset who had a mother with the education levels equal to less than high school (<12), high school (12), more than high school but not a college graduate (>12) and college degree.

This function should return a dictionary in the form of (use the correct numbers, do not round numbers):
#
The main objective of the code is to compute the proportions of children in a given dataset whose mothers have different levels of education, and save the results in a dictionary. This dictionary consists of four key-value pairs, where each key corresponds to a specific education level category and its corresponding value represents the proportion of children in the dataset with mothers who belong to that category. The code leverages the pandas library to read a CSV file, determine the frequency and proportions of each education level, and construct the dictionary, which is subsequently returned as the function's output. The assertions included at the end of the code are utilized to verify that the function returns a dictionary with the correct number of items and keys.
# Question 2
Let's explore the relationship between being fed breastmilk as a child and getting a seasonal influenza vaccine from a healthcare provider. Return a tuple of the average number of influenza vaccines for those children we know received breastmilk as a child and those who know did not.

This function should return a tuple in the form (use the correct numbers:
#
The purpose of this code is to compute the mean number of influenza doses that children received, based on whether their mothers answered "yes" or "no" to a particular question ("CBF_01") in the dataset. The code utilizes the pandas library to read a CSV file and filter the rows of the DataFrame based on the values in the "CBF_01" column. The average number of influenza doses is then computed for each filtered DataFrame using the mean() method applied to the "P_NUMFLU" column. The function returns a tuple that contains two values: the mean number of influenza doses for children whose mothers answered "yes" and the mean number of influenza doses for children whose mothers answered "no". The assertion statement at the end checks that the function indeed returns a tuple with exactly two values, as required.
# Question 3
It would be interesting to see if there is any evidence of a link between vaccine effectiveness and sex of the child. Calculate the ratio of the number of children who contracted chickenpox but were vaccinated against it (at least one varicella dose) versus those who were vaccinated but did not contract chicken pox. Return results by sex.

This function should return a dictionary in the form of (use the correct numbers):

    {"male":0.2,
    "female":0.4}
    #
    The chickenpox_by_sex() function analyzes data from the 'NISPUF17.csv' file to calculate the ratio of females and males who have had chickenpox. Here's a step-by-step review of the code:

import pandas as pd: This line imports the pandas library, which is a popular data manipulation library in Python.

df = pd.read_csv('assets/NISPUF17.csv'): This line reads a CSV file called 'NISPUF17.csv' and loads it into a Pandas DataFrame named df.

df = pd.read_csv('assets/NISPUF17.csv', index_col=0): This line reads the same CSV file and sets the first column as the index column of the DataFrame. The purpose of this line is unclear, as it overrides the previously loaded DataFrame df and the index column is not used further in the code. It can be removed.

df = df[["SEX", "HAD_CPOX", "P_NUMVRC"]].dropna(): This line creates a new DataFrame df by selecting only the "SEX", "HAD_CPOX", and "P_NUMVRC" columns from the original DataFrame, and then dropping any rows with missing values using the dropna() method. This is done to ensure that only rows with complete data in these three columns are included in the subsequent analysis.

df = df[df["P_NUMVRC"] > 0]: This line further filters the DataFrame by keeping only the rows where the value in the "P_NUMVRC" column is greater than 0, which means that the child has received at least one chickenpox vaccine dose. This is done to exclude children who have not received any chickenpox vaccine doses from the analysis.

male_df = df[df["SEX"] == 1]: This line creates a new DataFrame male_df by filtering the rows in the original DataFrame df where the value in the "SEX" column is equal to 1, which represents males.

female_df = df[df["SEX"] == 2]: This line creates a new DataFrame female_df by filtering the rows in the original DataFrame df where the value in the "SEX" column is equal to 2, which represents females.

female_chickenpox = female_df[(female_df["HAD_CPOX"] == 1) & (female_df["P_NUMVRC"] >= 1)]: This line creates a new DataFrame female_chickenpox by filtering the rows in the female_df DataFrame where the value in the "HAD_CPOX" column is equal to 1 (indicating that the child has had chickenpox) and the value in the "P_NUMVRC" column is greater than or equal to 1 (indicating that the child has received at least one chickenpox vaccine dose).

female_non_chickenpox = female_df[(female_df["HAD_CPOX"] == 2) & (female_df["P_NUMVRC"] >= 1)]: This line creates a new DataFrame female_non_chickenpox by filtering the rows in the female_df DataFrame where the value in the "HAD_CPOX" column is equal to 2 (indicating that the child has not had chickenpox) and the value in the "P_NUMVRC" column is greater than or equal to 1 (indicating that the child has received at least one chickenpox vaccine dose).

# Question 4
A correlation is a statistical relationship between two variables. If we wanted to know if vaccines work, we might look at the correlation between the use of the vaccine and whether it results in prevention of the infection or disease [1]. In this question, you are to see if there is a correlation between having had the chicken pox and the number of chickenpox vaccine doses given (varicella).

Some notes on interpreting the answer. The had_chickenpox_column is either 1 (for yes) or 2 (for no), and the num_chickenpox_vaccine_column is the number of doses a child has been given of the varicella vaccine. A positive correlation (e.g., corr > 0) means that an increase in had_chickenpox_column (which means more no’s) would also increase the values of num_chickenpox_vaccine_column (which means more doses of vaccine). If there is a negative correlation (e.g., corr < 0), it indicates that having had chickenpox is related to an increase in the number of vaccine doses.

Also, pval is the probability that we observe a correlation between had_chickenpox_column and num_chickenpox_vaccine_column which is greater than or equal to a particular value occurred by chance. A small pval means that the observed correlation is highly unlikely to occur by chance. In this case, pval should be very small (will end in e-18 indicating a very small number).

[1] This isn’t really the full picture, since we are not looking at when the dose was given. It’s possible that children had chickenpox and then their parents went to get them the vaccine. Does this dataset have the data we would need to investigate the timing of the dose?
#
The corr_chickenpox() function is designed to perform correlation analysis between two columns in a DataFrame using the pandas and scipy.stats libraries. Here's a step-by-step breakdown of the code:

import pandas as pd: This line imports the pandas library, which is a popular data manipulation library in Python.

from scipy.stats import pearsonr: This line imports the pearsonr() function from the scipy.stats module, which is used to compute the Pearson correlation coefficient.

def corr_chickenpox(): This line defines the corr_chickenpox() function.

df = pd.read_csv('assets/NISPUF17.csv'): This line reads a CSV file called 'NISPUF17.csv' and loads it into a Pandas DataFrame named df.

df = df[(df["HAD_CPOX"] <= 2) & (df["P_NUMVRC"].notnull()) & (df["HAD_CPOX"].notnull())]: This line filters the DataFrame by keeping only the rows where the value in the "HAD_CPOX" column is less than or equal to 2, and where neither the "P_NUMVRC" nor "HAD_CPOX" column values are null.

corr, pval= pearsonr(df["HAD_CPOX"], df["P_NUMVRC"]): This line computes the Pearson correlation coefficient between the "HAD_CPOX" and "P_NUMVRC" columns using the pearsonr() function, and assigns the result to the variables corr and pval.

return corr: This line returns the calculated correlation coefficient as the result.

assert isinstance(corr, float) and -1.0 <= corr <= 1.0, "Correlation coefficient should be a float between -1.0 and 1.0": This assertion statement checks if the returned value is a float between -1 and 1, which is the expected range for a correlation coefficient. If the assertion fails, an error message is displayed, indicating that the returned value should be a float between -1.0 and 1.0.

Overall, the function performs the necessary data cleaning and uses the pearsonr() function to calculate the correlation coefficient. The assertion statement ensures that the returned value is within the expected range, which is a good practice to ensure the correctness of the implementation.
