# UCI-data-correct-split

## Self Normalizing Neural Networks - Data Correct Splits

In the paper [Self Normalizing Neural Networks](https://arxiv.org/pdf/1706.02515), some datasets have inconsistencies in the number of classes across training, validation, and test splits. For example, the training dataset may contain six classes, while the test dataset only has five classes, and the validation dataset has four classes. In such cases, the validation metric score might not accurately predict the test results.

### Repository Contents

- **analysis_results.csv**: A summary file listing datasets with issues of 40 datasets.
- **33 UCI data correct splits.zip**: A zip file containing the correctly split datasets on 33 datasets.
- **problem_datasets.csv**: A file listing datasets with an issue of 2 instances in some class/label on 7 datasets
- **40 UCI datasets.zip**:  40 UCI datasets are listed in **analysis_result.csv**, where we corrected splits for 33 datasets, and 7 datasets had a low number of instances issues that could not be fixed by the stratified split.
- **EntireData** folder *EntireData* folder contains 121 datasets, divided into part1, part2, part3, and part4. \
      Or you can download from here-(33 corrected splits + 88 from SNN paper) [here](https://drive.google.com/file/d/1Ra4_ybcJI4O9ppCG0Ad33ZLqTlgC9rLi/view?usp=sharing).



### The Whole Dataset



### Correct Data Splits

The **UCI data correct splits.zip** file contains the corrected data splits using _StratifiedShuffleSplit_. The organization of these splits is consistent with the paper *Self Normalizing Neural Networks*, allowing you to use the same data loader file to load the data. The train/val/test data split ratio is 0.64/0.16/0.2.


### Datasets with issues Information

The file **analysis_results.csv** summarizes which datasets (40 datasets) have these issues, such as class label inconsistencies or too few data samples in certain classes. (each dataset may have four data splits; the file shows each split problem)

### Short Data Sample Problem
The file **problem_datasets.csv** contains information on datasets (7 datasets) where some classes/labels have only 2 instances. In such cases, we cannot perform _StratifiedShuffleSplit_ effectively.

### original data
The link access the other data and original ones [links](https://github.com/bioinf-jku/SNNs/tree/master/UCI)


### Usage

1. **Download the Files**: Download the **UCI data correct splits.zip** file and extract its contents.

2. **Load the Data**: Use the same data loader file provided in the *Self Normalizing Neural Networks* paper to load the corrected data splits.

### Example

To load a dataset, follow the example below:

```python
import numpy as np

# Load validation indices
val_file = np.loadtxt('path_to_extracted_folder/dataset_name/validation_py.dat', delimiter=',')

# Load test indices
fold_index = np.loadtxt('path_to_extracted_folder/dataset_name/folds_py.dat', delimiter=',')


### Reference results

| Dataset                        | SVM      | adaboost | bagging  | decision_tree | extratree | randomforest | stack    | voting   |
|--------------------------------|----------|----------|----------|---------------|-----------|--------------|----------|----------|
| annealing                      | 0.827778 | 0.858333 | 0.945833 | 0.95          | 0.923611  | 0.938889     | 0.918056 | 0.852778 |
| breast-cancer-wisc-diag        | 0.966549 | 0.957746 | 0.961268 | 0.93662       | 0.948944  | 0.954225     | 0.97007  | 0.973592 |
| breast-cancer-wisc-prog        | 0.826531 | 0.785714 | 0.770408 | 0.673469      | 0.790816  | 0.780612     | 0.816327 | 0.80102  |
| congressional-voting           | 0.607798 | 0.616972 | 0.600917 | 0.600917      | 0.614679  | 0.603211     | 0.607798 | 0.594037 |
| conn-bench-sonar-mines-rocks   | 0.831731 | 0.759615 | 0.807692 | 0.701923      | 0.822115  | 0.783654     | 0.793269 | 0.807692 |
| conn-bench-vowel-deterding     | 0.995671 | 0.58171  | 0.971861 | 0.785173      | 0.996212  | 0.972403     | 0.961039 | 0.917208 |
| credit-approval                | 0.87064  | 0.854651 | 0.87064  | 0.866279      | 0.875     | 0.87936      | 0.857558 | 0.857558 |
| cylinder-bands                 | 0.779297 | 0.744141 | 0.851563 | 0.726563      | 0.785156  | 0.816406     | 0.730469 | 0.75     |
| dermatology                    | 0.972973 | 0.959459 | 0.962838 | 0.956081      | 0.976351  | 0.976351     | 0.986486 | 0.976351 |
| flags                          | 0.49359  | 0.512821 | 0.660256 | 0.519231      | 0.647436  | 0.628205     | 0.525641 | 0.538462 |
| heart-cleveland                | 0.594262 | 0.577869 | 0.610656 | 0.569672      | 0.577869  | 0.569672     | 0.581967 | 0.569672 |
| heart-hungarian                | 0.85274  | 0.821918 | 0.84589  | 0.808219      | 0.85274   | 0.832192     | 0.80137  | 0.818493 |
| heart-va                       | 0.2875   | 0.23125  | 0.2875   | 0.25625       | 0.2875    | 0.275        | 0.3      | 0.31875  |
| hepatitis                      | 0.865385 | 0.820513 | 0.801282 | 0.769231      | 0.833333  | 0.826923     | 0.769231 | 0.814103 |
| horse-colic                    | 0.841912 | 0.834559 | 0.860294 | 0.830882      | 0.838235  | 0.871324     | 0.856618 | 0.838235 |
| ionosphere                     | 0.934659 | 0.926136 | 0.931818 | 0.886364      | 0.917614  | 0.926136     | 0.923295 | 0.934659 |
| libras                         | 0.885417 | 0.611111 | 0.809028 | 0.534722      | 0.833333  | 0.798611     | 0.732639 | 0.777778 |
| molec-biol-promoter            | 0.836538 | 0.855769 | 0.865385 | 0.788462      | 0.846154  | 0.836538     | 0.855769 | 0.826923 |
| oocytes_merluccius_nucleus_4d  | 0.830392 | 0.77451  | 0.786275 | 0.735294      | 0.779412  | 0.773529     | 0.77451  | 0.772549 |
| oocytes_merluccius_states_2f   | 0.916667 | 0.858824 | 0.909804 | 0.882353      | 0.909804  | 0.905882     | 0.908824 | 0.901961 |
| oocytes_trisopterus_nucleus_2f | 0.830044 | 0.783991 | 0.791667 | 0.736842      | 0.811404  | 0.788377     | 0.801535 | 0.798246 |
| oocytes_trisopterus_states_5b  | 0.939891 | 0.814208 | 0.898907 | 0.881148      | 0.903005  | 0.898907     | 0.922131 | 0.927596 |
| parkinsons                     | 0.913265 | 0.877551 | 0.872449 | 0.80102       | 0.882653  | 0.892857     | 0.821429 | 0.867347 |
| planning                       | 0.711111 | 0.666667 | 0.661111 | 0.661111      | 0.7       | 0.672222     | 0.683333 | 0.627778 |
| primary-tumor                  | 0.420455 | 0.30303  | 0.424242 | 0.409091      | 0.454545  | 0.450758     | 0.481061 | 0.44697  |
| spectf                         | 0.919786 | 0.919786 | 0.919786 | 0.918449      | 0.919786  | 0.919786     | 0.919786 | 0.919786 |
| statlog-australian-credit      | 0.681686 | 0.686047 | 0.674419 | 0.670058      | 0.671512  | 0.670058     | 0.674419 | 0.670058 |
| statlog-german-credit          | 0.739    | 0.736    | 0.755    | 0.717         | 0.754     | 0.774        | 0.744    | 0.765    |
| statlog-heart                  | 0.828358 | 0.843284 | 0.809701 | 0.839552      | 0.850746  | 0.843284     | 0.83209  | 0.873134 |
| statlog-image                  | 0.961438 | 0.866984 | 0.974437 | 0.951473      | 0.97747   | 0.975737     | 0.964471 | 0.962305 |
| statlog-vehicle                | 0.804502 | 0.64218  | 0.75     | 0.693128      | 0.744076  | 0.731043     | 0.772512 | 0.757109 |
| synthetic-control              | 0.993333 | 0.876667 | 0.981667 | 0.883333      | 0.985     | 0.981667     | 0.995    | 0.991667 |
| wine                           | 0.971591 | 0.954545 | 0.965909 | 0.880682      | 0.994318  | 0.982955     | 0.971591 | 0.960227 |
| zoo                            | 0.940476 | 0.880952 | 0.964286 | 0.928571      | 0.952381  | 0.964286     | 0.916667 | 0.940476 |
| pittsburg-bridges-REL-L        | 0.630952 | 0.642857 | 0.714286 | 0.72619       | 0.642857  | 0.690476     | 0.595238 | 0.607143 |
| plant-texture                  | 0.835156 | 0.428906 | 0.813281 | 0.454688      | 0.83125   | 0.804688     | 0.816406 | 0.795313 |
| pittsburg-bridges-MATERIAL     | 0.829545 | 0.829545 | 0.886364 | 0.840909      | 0.875     | 0.875        | 0.795455 | 0.897727 |
| plant-shape                    | 0.679688 | 0.226563 | 0.59375  | 0.411719      | 0.620313  | 0.596875     | 0.565625 | 0.555469 |
| yeast                          | 0.619529 | 0.449495 | 0.607744 | 0.569024      | 0.616162  | 0.628788     | 0.61532  | 0.617003 |
| breast-tissue                  | 0.715909 | 0.647727 | 0.625    | 0.613636      | 0.681818  | 0.704545     | 0.727273 | 0.681818 |
| wine-quality-white             | 0.584439 | 0.471939 | 0.670663 | 0.548724      | 0.673469  | 0.659949     | 0.568112 | 0.579082 |
| glass                          | 0.69186  | 0.604651 | 0.761628 | 0.784884      | 0.738372  | 0.77907      | 0.686047 | 0.715116 |
| pittsburg-bridges-TYPE         | 0.583333 | 0.535714 | 0.607143 | 0.583333      | 0.619048  | 0.607143     | 0.571429 | 0.595238 |
| plant-margin                   | 0.810156 | 0.382031 | 0.832031 | 0.425         | 0.846094  | 0.788281     | 0.803125 | 0.79375  |
| pittsburg-bridges-T-OR-D       | 0.845238 | 0.845238 | 0.845238 | 0.809524      | 0.845238  | 0.833333     | 0.857143 | 0.869048 |

Compared algorithms are from *https://scikit-learn.org/stable/auto_examples/classification/index.html*
