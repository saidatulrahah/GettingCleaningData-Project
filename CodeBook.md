 Source of data for this project: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

# This R script does the following:

Source of the original data: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

Original description: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

The attached R script (run_analysis.R) performs the following to clean up the data:

# 1. Merges the training and the test sets to create one data set.
	-merge in X file for : train/x_train.txt with test/x_test.txt ("Number of Instances: 10299" and "Number of Attributes: 561" - for features)
	-merge in Y file for : train/y_train.txt with test/y_test.txt (10299x1 data frame with activity IDs.)
	-merge in S file for : train/subject_train.txt with test/subject_test.txt (10299x1 data frame with subject IDs)
	-merge all the data and write in merged_data.txt

# 2. Extracts only the measurements on the mean and standard deviation for each measurement.
	-Reads features.txt and extracts only the measurements on the mean and standard deviation for each measurement. 
	-The result is a 10299x66 data frame, because only 66 out of 561 attributes are measurements on the mean and standard deviation. All measurements appear to be floating point numbers in the range (-1, 1).

# 3. Uses descriptive activity names to name the activities in the data set.
	-Reads activity_labels.txt and applies descriptive activity names to name the activities in the data set:
		-walking
		-walkingupstairs
		-walkingdownstairs
		-sitting
		-standing
		-laying

# 4. Appropriately labels the data set with descriptive activity names.
	-The script also appropriately labels the data set with descriptive names: all feature names (attributes) and activity names are converted to lower case, underscores and brackets () are removed. Then it merges the 10299x66 data frame containing features with 10299x1 data frames containing activity labels and subject IDs. The result is saved as merged_clean_data.txt, a 10299x68 data frame such that the first column contains subject IDs, the second column activity names, and the last 66 columns are measurements. Subject IDs are integers between 1 and 30 inclusive. The names of the attributes are similar to the following:

		-tbodyacc-mean-x 
		-tbodyacc-mean-y 
		-tbodyacc-mean-z 
		-tbodyacc-std-x 
		-tbodyacc-std-y 
		-tbodyacc-std-z 
		-tgravityacc-mean-x 
		-tgravityacc-mean-y

# 5. Creates a 2nd, independent tidy data set with the average of each variable for each activity and each subject.
	-The script creates a 2nd, independent tidy data set with the average of each measurement for each activity and each subject. The result is saved as tidydata.txt, a 180x68 data frame, where as before, the first column contains subject IDs, the second column contains activity names (see below), and then the averages for each of the 66 attributes are in columns 3...68. There are 30 subjects and 6 activities, thus 180 rows in this data set with averages.


