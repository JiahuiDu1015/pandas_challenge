Using Pandas and Jupyter Notebook, create a report that includes the following data. The report includes a written description of at least two observable trends based on the data. 

Local Government Area (LGA) Summary

Perform the necessary calculations and then create a high-level snapshot of the local government area's key metrics in a DataFrame.

Include the following:

    Total number of unique schools

    Total students

    Total budget

    Average maths score

    Average reading score

    % passing maths (the percentage of students who passed maths)

    % passing reading (the percentage of students who passed reading)

    % overall passing (the percentage of students who passed maths AND reading)

    Note: A passing grade is 50 or higher.

School Summary

Perform the necessary calculations and then create a DataFrame that summarises key metrics about each school.

Include the following:

    School name

    School type

    Total students

    Total school budget

    Per student budget

    Average maths score

    Average reading score

    % passing maths (the percentage of students who passed maths)

    % passing reading (the percentage of students who passed reading)

    % overall passing (the percentage of students who passed maths AND reading)

Highest-Performing Schools (by % Overall Passing)
    
    Sort the schools by % Overall Passing in descending order and display the top 5 rows.
    
    Save the results in a DataFrame called "top_schools".

Lowest-Performing Schools (by % Overall Passing)
    
    Sort the schools by % Overall Passing in ascending order and display the top 5 rows.

    Save the results in a DataFrame called "bottom_schools".

Maths Scores by Year
    
    Perform the necessary calculations to create a DataFrame that lists the average maths score for students of each year level (9, 10, 11, 12) at each school.

Reading Scores by Year
    
    Create a DataFrame that lists the average reading score for students of each year level (9, 10, 11, 12) at each school.

Scores by School Spending
    
    Create a table that breaks down school performance based on average spending ranges (per student).

    Use the code provided below to create four bins with reasonable cutoff values to group school spending.

        spending_bins = [0, 585, 630, 645, 680]
      
        labels = ["<$585", "$585-630", "$630-645", "$645-680"]

Use pd.cut to categorise spending based on the bins.

Use the following code to then calculate mean scores per spending range.

        spending_maths_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Maths Score"].mean()
        
        spending_reading_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Reading Score"].mean()
        
        spending_passing_maths = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Maths"].mean()
        
        spending_passing_reading = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Reading"].mean()

        overall_passing_spending = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Overall Passing"].mean()

Use the scores above to create a DataFrame called spending_summary.

Include the following metrics in the table:

    Average maths score

    Average reading score

    % passing maths (the percentage of students who passed maths)

    % passing reading (the percentage of students who passed reading)

    % overall passing (the percentage of students who passed maths AND reading)

Scores by School Size

  Use the following code to bin the per_school_summary.

        size_bins = [0, 1000, 2000, 5000]
    
        labels = ["Small (<1000)", "Medium (1000-2000)", "Large (2000-5000)"]
  
  Use pd.cut on the "Total Students" column of the per_school_summary DataFrame.

  Create a DataFrame called size_summary that breaks down school performance based on school size (small, medium, or large).

Scores by School Type
  
  Use the per_school_summary DataFrame from the previous step to create a new DataFrame called type_summary.

  This new DataFrame should show school performance based on the "School Type".
