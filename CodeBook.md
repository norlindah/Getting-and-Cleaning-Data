
<h1>GETTING AND CLEANING DATA PROJECT</h1>

<h2>Description</h2>

<p>Information about the variables, data and transformations used in the course project for the Johns Hopkins Getting and Cleaning Data course.</p>

<h3>Source Data</h3>

<p>(https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)</p>

<h4>Activities</h4>

<p>The script run_Analysis.R performs the 5 steps described in the course project's definition.
1.	First, all the similar data is merged using the rbind() function. By similar, we address those files having the same number of columns and referring to the same entities.</p>
<p>2.	Then, only those columns with the mean and standard deviation measures are taken from the whole dataset. After extracting these columns, they are given the correct names, taken from features.txt.</p>
<p>3.	As activity data is addressed with values 1:6, we take the activity names and IDs from activity_labels.txt and they are substituted in the dataset. Label  the column name “Activity”.</p>
<p>4.	On the whole dataset, those columns with vague column names are corrected.</p>
<p>5.	Finally, we generate a new dataset with all the average measures for each subject and activity type (30 subjects * <p>6 activities = 180 rows). The output file is called averages_data.txt, and uploaded to this repository.
</p>

<h5>Variables</h5>

<p>x_train, y_train, x_test, y_test, subject_train and subject_test contain the data from the downloaded files.
x_data, y_data and subject_data merge the previous datasets to further analysis.</p>
<p>features contains the correct names for the x_data dataset, which are applied to the column names stored in mean_and_std_features, a numeric vector used to extract the desired data.</p>
<p>A similar approach is taken with activity names through the activities variable.
all_data merges x_data, y_data and subject_data in a big dataset.</p>
<p>Finally, averages_data contains the relevant averages which will be later stored in a .txt file. ddply() from the plyr package is used to apply colMeans() and ease the development.
</p>
