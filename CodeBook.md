# Code Book

## Variables

### `subject`
- Identification number for the subject who performed the activity.
- Integer values ranging from 1 to 30.

### `activity`
- Descriptive name of the activity performed by the subject.
- Six possible values: "WALKING", "WALKING_UPSTAIRS", "WALKING_DOWNSTAIRS", "SITTING", "STANDING", "LAYING".

### `TimeBodyAccelerometerMean-X`
- Mean of time-domain body accelerometer signal in the X direction.
- Numeric values.

### `TimeBodyAccelerometerMean-Y`
- Mean of time-domain body accelerometer signal in the Y direction.
- Numeric values.

### `...` (similar variables for other axes and signal types)

### `FrequencyBodyGyroscopeSTD-Z`
- Standard deviation of frequency-domain body gyroscope signal in the Z direction.
- Numeric values.

## Data

- The data is sourced from the UCI Human Activity Recognition Using Smartphones Dataset.
- It includes measurements from the accelerometer and gyroscope for various activities performed by subjects.

## Transformations and Work

1. **Merging Datasets:**
   - The training and test sets are merged into a single dataset (`data`), combining subjects, activities, and feature measurements.

2. **Extracting Relevant Measurements:**
   - Only the measurements related to the mean and standard deviation for each measurement are extracted into a new dataset (`TidyData`).

3. **Descriptive Activity Names:**
   - Descriptive activity names are used to replace activity codes in the `TidyData` dataset.

4. **Labeling Descriptive Variable Names:**
   - Variable names are appropriately labeled for better readability and understanding of the data.
   - Patterns such as "Acc" are replaced with "Accelerometer," "Gyro" with "Gyroscope," "BodyBody" with "Body," etc.
   - Prefixes like "t" and "f" are replaced with "Time" and "Frequency," respectively.
   - "-mean()" is replaced with "Mean," "-std()" with "STD," and "-freq()" with "Frequency."
   - Some terms are capitalized for consistency and clarity.

5. **Creating a Tidy Data Set:**
   - A new tidy dataset (`FinalData`) is created, summarizing the average of each variable for each activity and each subject.
   - Grouped by subject and activity, the dataset is summarized using the mean function.

6. **Writing the Tidy Data Set to a File:**
   - The final tidy dataset (`FinalData`) is written to a text file named "tidyData.txt," excluding row names.