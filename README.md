# Getting and Cleaning Data Project Assignment 
Project assignment for Getting and Cleaning Data

### You Need to run 'run_analysis.R' in the same directory where the extracted 'UCI HAR Dataset' folder 
### is located.

##### The source code will go over the required steps  by Getting and Cleaning Project 
#####  to produce two tidy data based on two sets of data (Training and Test)

You should create one R script called run_analysis.R that does the following. 
- Merges the training and the test sets to create one data set.
- Extracts only the measurements on the mean and standard deviation for each measurement. 
- Uses descriptive activity names to name the activities in the data set
- Appropriately labels the data set with descriptive variable names. 
- From the data set in step 4, creates a second, independent tidy data set with the average of each variable for 

each activity and each subject.

---------------
####  Orignal Data extracted from URL : 
#####  https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 

##  Libraries used in this Code
```{r}
library(data.table)
library(dplyr)
```
### Read Required Files from UCI HAR Dataset
# Variables and activties Labels:
```{r}
featureLabels <- read.table("UCI HAR Dataset/features.txt")
activityLabels <- read.table("UCI HAR Dataset/activity_labels.txt", header = FALSE)
```
### Train Data:
```{r}
subjectTrain <- read.table("UCI HAR Dataset/train/subject_train.txt", header = FALSE)
y_train <- read.table("UCI HAR Dataset/train/y_train.txt", header = FALSE)
X_train <- read.table("UCI HAR Dataset/train/X_train.txt", header = FALSE)
```
### Test Data:
```{r}
subjectTest <- read.table("UCI HAR Dataset/test/subject_test.txt", header = FALSE)
y_test <- read.table("UCI HAR Dataset/test/y_test.txt", header = FALSE)
X_test <- read.table("UCI HAR Dataset/test/X_test.txt", header = FALSE)
```
# First : Merges the training and the test sets to create one data set.
```{r}
subject <- rbind(subjectTrain, subjectTest)
features <- rbind(X_train, X_test)
activities <- rbind(y_train, y_test)

# Name the columns in each table
colnames(activities ) <- "Activity"
colnames(subject) <- "Subject"
colnames(features) <- t(featureLabels[2])

# put all data together as one table

dataSet <- cbind(subject,activities,features)
```
##### Assignment require merging all data set together than filtering
##### by required columns, code could be improve by filter before merging 
##### the whole data set.


# Second : Extracts only the measurements on the mean and standard deviation for each measurement.
```{r}
requiredColumns <- grep(".*Mean.*|.*Std.*", names(dataSet), ignore.case=TRUE)

# the above will give Mean and Std columns, we need also Subject and Activities columns
# when extracting the data

requiredDataSet <- dataSet[,c(1,2,requiredColumns)]
```

# Third: Uses descriptive activity names to name the activities in the data set
```{r}
requiredDataSet$Activity <- as.character(requiredDataSet$Activity)
for (i in 1:6){
requiredDataSet$Activity[requiredDataSet$Activity == i] <- as.character(activityLabels[i,2])
}

requiredDataSet$Activity <- as.factor(requiredDataSet$Activity)
```
# Fourth: Appropriately labels the data set with descriptive variable names. 

##### Here we need to replace the abbreviations used in variables with full descriptive variable names
##### information about the abbreviations could be found in the "features_info.txt":
# 
```{r}
names(requiredDataSet)<-gsub("Acc", "Accelerometer", names(requiredDataSet))
names(requiredDataSet)<-gsub("Gyro", "Gyroscope", names(requiredDataSet))
names(requiredDataSet)<-gsub("^t", "Time", names(requiredDataSet))
names(requiredDataSet)<-gsub("Mag", "Magnitude", names(requiredDataSet))
names(requiredDataSet)<-gsub("^f", "Frequency", names(requiredDataSet))
names(requiredDataSet)<-gsub("tBody", "TimeBody", names(requiredDataSet))
names(requiredDataSet)<-gsub("-mean()", "Mean", names(requiredDataSet), ignore.case = TRUE)
names(requiredDataSet)<-gsub("-std()", "STD", names(requiredDataSet), ignore.case = TRUE)
names(requiredDataSet)<-gsub("-freq()", "Frequency", names(requiredDataSet), ignore.case = TRUE)
names(requiredDataSet)<-gsub("Freq()", "Frequency", names(requiredDataSet), ignore.case = TRUE)
names(requiredDataSet)<-gsub("\\(|\\)", "", names(requiredDataSet), ignore.case = TRUE)
```


# Fifth Finally :) From the data set in step 4, creates a second, independent tidy data set 
##### with the average of each variable for each activity and each subject.
# 
# 
```{r}
requiredDataSet$Subject <- as.factor(requiredDataSet$Subject)
requiredDataSet <- data.table(requiredDataSet)

tidyData <- aggregate(. ~Subject + Activity, requiredDataSet, mean)

write.table(tidyData, file = "Tidy.txt", row.names = FALSE)
```





