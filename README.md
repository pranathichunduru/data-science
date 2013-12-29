# Instructions for usage

[Explanation of some of these scripts can be found on my weblog.](http://cowlet.org) Below is the quick guide to getting them running.


## `basic_feature_extraction.R`

1.  Download the [open bearing dataset](http://ti.arc.nasa.gov/c/3/).

2.  Move the `bearing_IMS` directory to the same level as the `bearing_snippets` directory OR
    
    Modify the first line of the script to point basedir to the `bearing_IMS/1st_test` directory.

3.  Run `basic_feature_extraction.R`! This writes the basic feature vectors to `b1.csv` through `b4.csv`.


## `basic_feature_graphing.R`

1.  For the first time through, run `basic_feature_extraction.R` to generate the features. Thereafter, the features are written to files `b1.csv`, `b2.csv`, `b3.csv`, and `b4.csv`, and you can go straight to step 2.

2.  Run `basic_feature_graphing.R`! 


## `more_features.R`

1.  Perform steps 1 and 2 of `basic_feature_extraction.R`.

2.  Run `more_features.R`! This writes the full feature vectors to `b1_all.csv` through `b4_all.csv`.


## `feature_correlation.R`

1.  Run `more_features.R`, so the features are stored in files `b1_all.csv` through `b4_all.csv`.

2.  Run `feature_correlation.R`, to see features with high correlation.

## `optimise.rb`

1.  Run `feature_correlation.R` to output sets of features with high correlation.

2.  Run `optimise.rb` to select the minimal set of uncorrelated features.


## `feature_information.R`

1.  Run `more_features.R`, so the features are stored in files `b1_all.csv` through `b4_all.csv`.

2.  If desired, modify line 25 of `feature_information.R` to include only the features you are interested in (e.g. after running `optimise.rb` and finding a different minimal set).

3.  Run `feature_information.R` to generate an interesting graph! It also writes the full feature vector plus state labels to `all_bearings.csv`, and the best 14 features plus state labels to `all_bearings_best_fv.csv`.


## `kmeans.R`

1.  Run `feature_information.R`, so the minimised set of features are written to `all_bearings_best_fv.csv`.

2.  Run `kmeans.R` to select the best k-means model! It also writes it to `kmeans.obj`.


## `relabel.R`

1.  Run `feature_information.R`, so the minimised set of features are written to `all_bearings_best_fv.csv`.

2.  Run `kmeans.R`, so the best k-means model is written to `kmeans.obj`.

3.  Visualise the results using the graphs generated by `kmeans.R`. Alter the filename on line 7 to match the best k-means model. If needed, alter the cluster numbers or class labels in `relabel.R` to better match the data.

3.  Run `relabel.R` to modify the state labels. It also plots a state transition graph, and writes the new data to `all_bearings_relabelled.csv`.

