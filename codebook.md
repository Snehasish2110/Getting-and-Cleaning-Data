For the project of getting and cleaning data, First I downloaded the file and save in a directory called Data and unzipped the files.After Unziiping, i get the list of files available in the directory UCI HAR Dataset. The details of the dataset are given in readme.txt files. For the purposes of this project, the files in the Inertial Signals folders are not used. The files that will be used to load data are listed as follows:

test/subject_test.txt
test/X_test.txt
test/y_test.txt
train/subject_train.txt
train/X_train.txt
train/y_train.txt

From the related files description,we can see:

Values of Varible Activity consist of data from "Y_train.txt" and "Y_test.txt"
values of Varible Subject consist of data from "subject_train.txt" and subject_test.txt"
Values of Varibles Features consist of data from "X_train.txt" and "X_test.txt"
Names of Varibles Features come from "features.txt"
levels of Varible Activity come from "activity_labels.txt"

So I used Activity, Subject and Features as part of descriptive variable names for data in data frame.

Then read the train and test activity, subject and  features files and store them into variables.

Then I used STR function to look at the properties of each variables/data.frame. After that, merged the training and test dataset to get one dataset using rbind function. After merging, set names of the each dataframe in the next command. Then, using cbind, merged column and created a dataframe called "data" for all the data. 

As the course project only required only mean and standard deviation for each measurement, I subset the name of fetures by measurements of mean and standard deviation and subset the dataframe "data" based of name of features. After that, check the structure of the data using STR function

Then, I have read activity name from "activity.txt" file and mapped them with the activity in the original data.frame "data" file.  Following are the activity no. and Activity Name:

1 WALKING
2 WALKING_UPSTAIRS
3 WALKING_DOWNSTAIRS
4 SITTING
5 STANDING
6 LAYING


In the former part, variables activity and subject and names of the activities have been labelled using descriptive names.So, now, Names of Features will labelled using descriptive variable names. Following are names given to the features:

prefix t is replaced by time
Acc is replaced by Accelerometer
Gyro is replaced by Gyroscope
prefix f is replaced by frequency
Mag is replaced by Magnitude
BodyBody is replaced by Body

After that, I have created independent tidy dataset using average of each variable for each activity and each subject based on the data and the output is saved in "tidydata.txt" file.


