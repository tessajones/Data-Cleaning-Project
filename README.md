# Data-Cleaning-Project

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details.

==================================================================


run_analysis.R function

Imports the data and exports two text files.  All_data.txt is a list of subject, activities, and measurements. 

All_data_sum.txt is an aggregated summary of each subject for each activity.  


***working directory should include UCIHAR Dataset folder and all of the folders and files listed below*** 

UCIHAR Dataset (folder) containing : activity_labels.txt, features.txt, test (folder), train (folder)

train folder (within UCIHAR Dataset) should include: 	X_train.txt, y_train.txt, subject_train.txt

test folder (within UCIHAR Dataset) should include: 	X_test.txt, y_test.txt, subject_test.txt


===================================================================

Script Operations

Import files include: 

X_train.txt and y_test.txt (which is the measurement data)
y_train.txt and y_test.txt (list of activities as numeric values)
subject_train.txt and subject_test.txt (list of subjects as numeric values)
features.txt (which is the column names for the data set)

run_analysis.R Imports the information from the text files into variables in the script.  

X(variable) is the actual measurement data.
Y(variable) is the activities numbers  
S(variable) is a list of subjects that did the activity (as a numerical value).  

Each subject did each activity and there are mean and standard deviation data associated with each combinations of subject and activity.  
  

The data labels were extracted from features.txt and turned into the column headers for X.  The column names were cleaned up (paranthesis removed and turned 
into all lower case letters).

labels(variable) is the measurement titles.

the activity labels were extracted from activity_labels.txt to correlate numbers to activities.

activities(variable) is the activities and there numeric values

1 is Walking
2 is WALKING_UPSTAIRS
3 IS WALKING_DOWNSTAIRS
4 IS SITTING
5 IS STANDING
6 IS LAYING

the activity titles were converted to lower case.  The number variables from Y that correlate to activities was combined with the activities variable so that all 
activities could be labelled.  The column was named activity.

The S variable column was named subject and it was merged with Y and X and exported as a txt file called "All_data.txt".  This file includes the subjects, the activities and the measurements.  

A results table is created with all of the entries for each subject and all of their activities.

A for loop was created to generate the mean of each measurement column for each subject for each activity.  The total number of entries should equal the number of subjects 
multiplied by the number of activities.  30 subjects * 6 activities = 180 rows.  The data was exported as "All_data_sum.txt"
