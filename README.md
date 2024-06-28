# UCI-data-correct-split

## Self Normalizing Neural Networks - Data Correct Splits

In the paper [Self Normalizing Neural Networks](https://arxiv.org/pdf/1706.02515), some datasets have inconsistencies in the number of classes across training, validation, and test splits. For example, the training dataset may contain six classes, while the test dataset only has five classes, and the validation dataset has four classes. In such cases, the validation metric score might not accurately predict the test results.

### Repository Contents

- **analysis_results.csv**: A summary file listing datasets with issues of 40 datasets.
- **UCI data correct splits.zip**: A zip file containing the correctly split datasets on 33 datasets.
- **problem_datasets.csv**: A file listing datasets with an issue of 2 instances in some class/label on 7 datasets
- **40 UCI datasets.zip**:  40 UCI datasets are listed in **analysis_result.csv**, where we corrected splits for 33 datasets, and 7 datasets had a low number of instances issues that could not be fixed by the stratified split.



### The Whole Dataset
The entire dataset (33 corrected splits + 88 from SNN paper) can be found [here](https://drive.google.com/file/d/18AI01FxMaGcR6onxtG-EE63C1g7IfgtE/view?usp=drive_link).


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
