CodeBook
---------------------------------------------------------------
# 
# 


The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 

For each record it is provided:
======================================

- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.

##### The Following represent the variables names used for Tidy data output
## Variables:


 [1] "Subject"  1:30 representing the subject                                                    
 [2] "Activity" list of (WALKING
, WALKING_UPSTAIRS
, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING
)                       
 [3] "TimeBodyAccelerometerMean-X"                                  
 [4] "TimeBodyAccelerometerMean-Y"                                  
 [5] "TimeBodyAccelerometerMean-Z"                                  
 [6] "TimeBodyAccelerometerSTD-X"                                   
 [7] "TimeBodyAccelerometerSTD-Y"                                   
 [8] "TimeBodyAccelerometerSTD-Z"                                   
 [9] "TimeGravityAccelerometerMean-X"                               
[10] "TimeGravityAccelerometerMean-Y"                               
[11] "TimeGravityAccelerometerMean-Z"                               
[12] "TimeGravityAccelerometerSTD-X"                                
[13] "TimeGravityAccelerometerSTD-Y"                                
[14] "TimeGravityAccelerometerSTD-Z"                                
[15] "TimeBodyAccelerometerJerkMean-X"                              
[16] "TimeBodyAccelerometerJerkMean-Y"                              
[17] "TimeBodyAccelerometerJerkMean-Z"                              
[18] "TimeBodyAccelerometerJerkSTD-X"                               
[19] "TimeBodyAccelerometerJerkSTD-Y"                               
[20] "TimeBodyAccelerometerJerkSTD-Z"                               
[21] "TimeBodyGyroscopeMean-X"                                      
[22] "TimeBodyGyroscopeMean-Y"                                      
[23] "TimeBodyGyroscopeMean-Z"                                      
[24] "TimeBodyGyroscopeSTD-X"                                       
[25] "TimeBodyGyroscopeSTD-Y"                                       
[26] "TimeBodyGyroscopeSTD-Z"                                       
[27] "TimeBodyGyroscopeJerkMean-X"                                  
[28] "TimeBodyGyroscopeJerkMean-Y"                                  
[29] "TimeBodyGyroscopeJerkMean-Z"                                  
[30] "TimeBodyGyroscopeJerkSTD-X"                                   
[31] "TimeBodyGyroscopeJerkSTD-Y"                                   
[32] "TimeBodyGyroscopeJerkSTD-Z"                                   
[33] "TimeBodyAccelerometerMagnitudeMean"                           
[34] "TimeBodyAccelerometerMagnitudeSTD"                            
[35] "TimeGravityAccelerometerMagnitudeMean"                        
[36] "TimeGravityAccelerometerMagnitudeSTD"                         
[37] "TimeBodyAccelerometerJerkMagnitudeMean"                       
[38] "TimeBodyAccelerometerJerkMagnitudeSTD"                        
[39] "TimeBodyGyroscopeMagnitudeMean"                               
[40] "TimeBodyGyroscopeMagnitudeSTD"                                
[41] "TimeBodyGyroscopeJerkMagnitudeMean"                           
[42] "TimeBodyGyroscopeJerkMagnitudeSTD"                            
[43] "FrequencyuencyBodyAccelerometerMean-X"                        
[44] "FrequencyuencyBodyAccelerometerMean-Y"                        
[45] "FrequencyuencyBodyAccelerometerMean-Z"                        
[46] "FrequencyuencyBodyAccelerometerSTD-X"                         
[47] "FrequencyuencyBodyAccelerometerSTD-Y"                         
[48] "FrequencyuencyBodyAccelerometerSTD-Z"                         
[49] "FrequencyuencyBodyAccelerometerMeanFrequency-X"               
[50] "FrequencyuencyBodyAccelerometerMeanFrequency-Y"               
[51] "FrequencyuencyBodyAccelerometerMeanFrequency-Z"               
[52] "FrequencyuencyBodyAccelerometerJerkMean-X"                    
[53] "FrequencyuencyBodyAccelerometerJerkMean-Y"                    
[54] "FrequencyuencyBodyAccelerometerJerkMean-Z"                    
[55] "FrequencyuencyBodyAccelerometerJerkSTD-X"                     
[56] "FrequencyuencyBodyAccelerometerJerkSTD-Y"                     
[57] "FrequencyuencyBodyAccelerometerJerkSTD-Z"                     
[58] "FrequencyuencyBodyAccelerometerJerkMeanFrequency-X"           
[59] "FrequencyuencyBodyAccelerometerJerkMeanFrequency-Y"           
[60] "FrequencyuencyBodyAccelerometerJerkMeanFrequency-Z"           
[61] "FrequencyuencyBodyGyroscopeMean-X"                            
[62] "FrequencyuencyBodyGyroscopeMean-Y"                            
[63] "FrequencyuencyBodyGyroscopeMean-Z"                            
[64] "FrequencyuencyBodyGyroscopeSTD-X"                             
[65] "FrequencyuencyBodyGyroscopeSTD-Y"                             
[66] "FrequencyuencyBodyGyroscopeSTD-Z"                             
[67] "FrequencyuencyBodyGyroscopeMeanFrequency-X"                   
[68] "FrequencyuencyBodyGyroscopeMeanFrequency-Y"                   
[69] "FrequencyuencyBodyGyroscopeMeanFrequency-Z"                   
[70] "FrequencyuencyBodyAccelerometerMagnitudeMean"                 
[71] "FrequencyuencyBodyAccelerometerMagnitudeSTD"                  
[72] "FrequencyuencyBodyAccelerometerMagnitudeMeanFrequency"        
[73] "FrequencyuencyBodyBodyAccelerometerJerkMagnitudeMean"         
[74] "FrequencyuencyBodyBodyAccelerometerJerkMagnitudeSTD"          
[75] "FrequencyuencyBodyBodyAccelerometerJerkMagnitudeMeanFrequency"
[76] "FrequencyuencyBodyBodyGyroscopeMagnitudeMean"                 
[77] "FrequencyuencyBodyBodyGyroscopeMagnitudeSTD"                  
[78] "FrequencyuencyBodyBodyGyroscopeMagnitudeMeanFrequency"        
[79] "FrequencyuencyBodyBodyGyroscopeJerkMagnitudeMean"             
[80] "FrequencyuencyBodyBodyGyroscopeJerkMagnitudeSTD"              
[81] "FrequencyuencyBodyBodyGyroscopeJerkMagnitudeMeanFrequency"    
[82] "angleTimeBodyAccelerometerMean,gravity"                       
[83] "angleTimeBodyAccelerometerJerkMean,gravityMean"               
[84] "angleTimeBodyGyroscopeMean,gravityMean"                       
[85] "angleTimeBodyGyroscopeJerkMean,gravityMean"                   
[86] "angleX,gravityMean"                                           
[87] "angleY,gravityMean"                                           
[88] "angleZ,gravityMean"             


## Data

##Dataset Used

This data is obtained from "Human Activity Recognition Using Smartphones Data Set". The data linked are collected from the accelerometers from the Samsung Galaxy S smartphone. A full description is available at the site <http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones>.

The dataset includes the following files:
=========================================

- 'README.txt'

- 'features_info.txt': Shows information about the variables used on the feature vector.

- 'features.txt': List of all features.

- 'activity_labels.txt': Links the class labels with their activity name.

- 'train/X_train.txt': Training set.

- 'train/y_train.txt': Training labels.

- 'test/X_test.txt': Test set.

- 'test/y_test.txt': Test labels.

- 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 


# Transformation

## Variables and activties Labels:

- featureLabels: table reading from 'features.txt'.

- activityLabels: table reading from 'activity_labels.txt'.

## Train Data:
- subjectTrain: table reading from 'subject_train.txt'
- y_train :table reading from 'y_train.txt'
- X_train :table reading from 'X_train.txt'

## Test Data:
- subjectTest: table reading from 'subject_test.txt'
- y_test : table reading from 'y_test.txt'
- X_test : table reading from 'X_test.txt'

## Merging tables
#### Combine rows of Test and Train data:
- subjectTrain and subjectTest was merged into subject 
- X_train and X_test was merged into features
- y_train and y_test was merged into activities

then we combine columns of subject,activities,features into one data set 'dataSet'

 the data then subseted based on the required columns of mean and STD into 'requiredDataSet'


## Output Data set:

'tidyData.txt' tidy data set with the average of each variable for each activity and each subject.