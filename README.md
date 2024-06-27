# UCI-data-correct-split

## Self Normalizing Neural Networks - Data Correct Splits

In the paper [Self Normalizing Neural Networks](https://arxiv.org/pdf/1706.02515), some datasets have inconsistencies in the number of classes across training, validation, and test splits. For example, the training dataset may contain six classes, while the test dataset only has five classes, and the validation dataset has four classes. In such cases, the validation metric score cannot accurately predict the test results.

### Summary Information

The file **analysis_results.csv** contains a summary of which datasets have these issues, such as class label inconsistencies or too few data samples in certain classes.

### The Whole Dataset
The entire dataset can be found [here](https://drive.google.com/file/d/18AI01FxMaGcR6onxtG-EE63C1g7IfgtE/view?usp=drive_link).

### Short Data Sample Problem
The file **problem_datasets.csv** contains information on datasets where some classes/labels have only 2 instances. In such cases, we cannot perform _StratifiedShuffleSplit_ effectively.

### original data
The link access the other data and original ones [links](https://github.com/bioinf-jku/SNNs/tree/master/UCI)

### Correct Data Splits

The **UCI data correct splits.zip** file contains the corrected data splits using _StratifiedShuffleSplit_. The organization of these splits is consistent with the paper *Self Normalizing Neural Networks*, allowing you to use the same data loader file to load the data.

### Repository Contents

- **analysis_results.csv**: A summary file listing datasets with issues.
- **UCI data correct splits.zip**: A zip file containing the correctly split datasets.

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
