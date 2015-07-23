
Getting and Cleaning Data

Course Project
The purpose of this project is to demonstrate ability to collect, work with, and clean a data set. The goal is to prepare tidy data that can be used for later analysis.

Step 1:
Unzip the source data from 
https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip into a folder on your local drive,
 say C:\Users\yourname\Documents\Github\

Step 2:
In RStudio: setwd("C:\Users\yourname\Documents\Github\UCI HAR Dataset\")
R script named "run_analysis.R"  is saved in the working directory

run_analysis.R that does the following: 
Merges the training and the test sets to create one data set.
Extracts only the measurements on the mean and standard deviation for each measurement. 
Uses descriptive activity names to name the activities in the data set
Appropriately labels the data set with descriptive variable names. 
From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

Step 3
Use data <- read.table("tidydata.txt") to read the data. It is 180x68 because there are 30 subjects and 6 activities, thus "for each activity and each subject" means 30 * 6 = 180 rows
