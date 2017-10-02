
# Script Information

Code run_analysis.R executes the 5 steps described in 'Review criteria' 

## Step 1
Similar data is merged using the `rbind()` function. Files having the same number of columns and referring to the same entities are merged.

## Step 2
Columns with the mean and standard deviation measures are taken from the whole dataset. After extracting these columns, they are given the correct names, taken from `features.txt`.

## Step 3
Activity names and IDs are taken from `activity_labels.txt` and they are substituted in the dataset.

## Step 4
Columns with not proper column names are corrected.

## Step 5
Finally, a file called averages_data.txt containing a new dataset with all the average measures for each subject and activity type (30 subjects * 6 activities = 180 rows) is generated.

# Variable Information

* `x_train`, `y_train`, `x_test`, `y_test`, `subject_train` and `subject_test` contain the data from the downloaded files.
* `x_data`, `y_data` and `subject_data` merge the previous datasets for further analysis.
* `features` contains the correct names for the `x_data` dataset, which are applied to the column names stored in `meanAndStdFeatures`, a numeric vector used to extract the desired data.
* A similar approach is taken with activity names through the `activities` variable.
* `all_data` merges `x_data`, `y_data` and `subject_data` in a big dataset.
* Finally, `averages_data` contains the relevant averages which will be later stored in a `.txt` file. `ddply()` from the plyr package is used to apply `colMeans()` and ease the development.
