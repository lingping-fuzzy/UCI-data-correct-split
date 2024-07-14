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

- **Data meta information** The item Data Meta Information contains details such as the number of instances, feature size, etc., for all datasets. It also specifically indicates which datasets have the new split.

- **Results** This folder contains the running results from reference methods on 45 datasets of [Sklearn](https://scikit-learn.org/stable/auto_examples/classification/index.html), including XGBoost, random forest, etc. The metrics include accuracy, F1-score, recall, and precision.


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

### Data meta information
new split- where the dataset has corrected data splits using _StratifiedShuffleSplit_, then the rest of them are the same as the original paper,

the entire data is in a folder *Entire data*

| dataset                        | instances | labels_classes | features | Remark      | train size | vali size | test size |
|--------------------------------|-----------|----------------|----------|-----------|------------|-----------|-----------|
| abalone                        | 4177      | 3              | 8        |           | 2503       | 630       | 1044      |
| acute-inflammation             | 120       | 2              | 6        |           | 74         | 16        | 30        |
| acute-nephritis                | 120       | 2              | 6        |           | 73         | 17        | 30        |
| adult                          | 48842     | 2              | 14       |           | 25999      | 6562      | 16281     |
| annealing                      | 898       | 5              | 31       | new split | 574        | 144       | 180       |
| arrhythmia                     | 452       | 13             | 262      |           | 260        | 79        | 113       |
| audiology-std                  | 196       | 18             | 59       |           | 140        | 31        | 25        |
| balance-scale                  | 625       | 3              | 4        | new split | 400        | 100       | 125       |
| balloons                       | 16        | 2              | 4        | new split | 9          | 3         | 4         |
| bank                           | 4521      | 2              | 16       |           | 2690       | 701       | 1130      |
| blood                          | 748       | 2              | 4        |           | 439        | 122       | 187       |
| breast-cancer                  | 286       | 2              | 9        |           | 181        | 34        | 71        |
| breast-cancer-wisc             | 699       | 2              | 9        |           | 406        | 118       | 175       |
| breast-cancer-wisc-diag        | 569       | 2              | 30       |           | 347        | 80        | 142       |
| breast-cancer-wisc-prog        | 198       | 2              | 33       |           | 127        | 22        | 49        |
| breast-tissue                  | 106       | 6              | 9        | new split | 67         | 17        | 22        |
| car                            | 1728      | 4              | 6        |           | 1026       | 270       | 432       |
| cardiotocography-10clases      | 2126      | 10             | 21       |           | 1276       | 319       | 531       |
| cardiotocography-3clases       | 2126      | 3              | 21       |           | 1272       | 323       | 531       |
| chess-krvk                     | 28056     | 18             | 6        |           | 16816      | 4226      | 7014      |
| chess-krvkp                    | 3196      | 2              | 36       |           | 1933       | 464       | 799       |
| congressional-voting           | 435       | 2              | 16       |           | 269        | 57        | 109       |
| conn-bench-sonar-mines-rocks   | 208       | 2              | 60       |           | 123        | 33        | 52        |
| conn-bench-vowel-deterding     | 990       | 11             | 11       |           | 427        | 101       | 462       |
| connect-4                      | 67557     | 2              | 42       |           | 40417      | 10251     | 16889     |
| contrac                        | 1473      | 3              | 9        |           | 894        | 211       | 368       |
| credit-approval                | 690       | 2              | 15       |           | 418        | 100       | 172       |
| cylinder-bands                 | 512       | 2              | 35       |           | 302        | 82        | 128       |
| dermatology                    | 366       | 6              | 34       | new split | 233        | 59        | 74        |
| echocardiogram                 | 131       | 2              | 10       |           | 78         | 20        | 33        |
| ecoli                          | 336       | 8              | 7        |           | 198        | 54        | 84        |
| energy-y1                      | 768       | 3              | 8        |           | 472        | 104       | 192       |
| energy-y2                      | 768       | 3              | 8        |           | 460        | 116       | 192       |
| fertility                      | 100       | 2              | 9        | new split | 64         | 16        | 20        |
| flags                          | 194       | 8              | 28       | new split | 124        | 31        | 39        |
| glass                          | 214       | 6              | 9        | new split | 136        | 35        | 43        |
| haberman-survival              | 306       | 2              | 3        |           | 184        | 46        | 76        |
| hayes-roth                     | 160       | 3              | 3        | new split | 102        | 26        | 32        |
| heart-cleveland                | 303       | 5              | 13       | new split | 193        | 49        | 61        |
| heart-hungarian                | 294       | 2              | 12       |           | 187        | 34        | 73        |
| heart-switzerland              | 123       | 5              | 12       | new split | 78         | 20        | 25        |
| heart-va                       | 200       | 5              | 12       | new split | 128        | 32        | 40        |
| hepatitis                      | 155       | 2              | 19       |           | 93         | 23        | 39        |
| hill-valley                    | 1212      | 2              | 100      |           | 480        | 126       | 606       |
| horse-colic                    | 368       | 2              | 25       |           | 234        | 66        | 68        |
| ilpd-indian-liver              | 583       | 2              | 9        |           | 351        | 86        | 146       |
| image-segmentation             | 2310      | 7              | 18       |           | 160        | 50        | 2100      |
| ionosphere                     | 351       | 2              | 33       |           | 216        | 47        | 88        |
| iris                           | 150       | 3              | 4        |           | 92         | 21        | 37        |
| led-display                    | 1000      | 10             | 7        |           | 594        | 156       | 250       |
| lenses                         | 24        | 3              | 4        | new split | 15         | 4         | 5         |
| letter                         | 20000     | 26             | 16       |           | 11941      | 3059      | 5000      |
| libras                         | 360       | 15             | 90       | new split | 230        | 58        | 72        |
| low-res-spect                  | 531       | 9              | 100      |           | 316        | 82        | 133       |
| lung-cancer                    | 32        | 3              | 56       | new split | 20         | 5         | 7         |
| lymphography                   | 148       | 4              | 18       |           | 91         | 20        | 37        |
| magic                          | 19020     | 2              | 10       |           | 11412      | 2853      | 4755      |
| mammographic                   | 961       | 2              | 5        |           | 575        | 146       | 240       |
| miniboone                      | 130064    | 2              | 50       |           | 77904      | 19644     | 32516     |
| molec-biol-promoter            | 106       | 2              | 57       |           | 64         | 16        | 26        |
| molec-biol-splice              | 3190      | 3              | 60       |           | 1913       | 480       | 797       |
| monks-1                        | 556       | 2              | 6        |           | 89         | 35        | 432       |
| monks-2                        | 601       | 2              | 6        |           | 139        | 30        | 432       |
| monks-3                        | 554       | 2              | 6        |           | 90         | 32        | 432       |
| mushroom                       | 8124      | 2              | 21       |           | 4889       | 1204      | 2031      |
| musk-1                         | 476       | 2              | 166      |           | 281        | 76        | 119       |
| musk-2                         | 6598      | 2              | 166      |           | 3998       | 951       | 1649      |
| nursery                        | 12960     | 5              | 8        |           | 7802       | 1918      | 3240      |
| oocytes_merluccius_nucleus_4d  | 1022      | 2              | 41       |           | 606        | 161       | 255       |
| oocytes_merluccius_states_2f   | 1022      | 3              | 25       |           | 632        | 135       | 255       |
| oocytes_trisopterus_nucleus_2f | 912       | 2              | 25       |           | 573        | 111       | 228       |
| oocytes_trisopterus_states_5b  | 912       | 3              | 32       | new split | 583        | 146       | 183       |
| optical                        | 5620      | 10             | 62       |           | 3060       | 763       | 1797      |
| ozone                          | 2536      | 2              | 72       |           | 1543       | 359       | 634       |
| page-blocks                    | 5473      | 5              | 10       | new split | 3502       | 876       | 1095      |
| parkinsons                     | 195       | 2              | 22       |           | 114        | 32        | 49        |
| pendigits                      | 10992     | 10             | 16       |           | 5996       | 1498      | 3498      |
| pima                           | 768       | 2              | 8        |           | 459        | 117       | 192       |
| pittsburg-bridges-MATERIAL     | 106       | 3              | 7        | new split | 67         | 17        | 22        |
| pittsburg-bridges-REL-L        | 103       | 3              | 7        | new split | 65         | 17        | 21        |
| pittsburg-bridges-SPAN         | 92        | 3              | 7        | new split | 58         | 15        | 19        |
| pittsburg-bridges-T-OR-D       | 102       | 2              | 7        | new split | 64         | 17        | 21        |
| pittsburg-bridges-TYPE         | 105       | 6              | 7        | new split | 67         | 17        | 21        |
| planning                       | 182       | 2              | 12       |           | 110        | 27        | 45        |
| plant-margin                   | 1600      | 100            | 64       | new split | 1024       | 256       | 320       |
| plant-shape                    | 1600      | 100            | 64       | new split | 1024       | 256       | 320       |
| plant-texture                  | 1599      | 100            | 64       | new split | 1023       | 256       | 320       |
| post-operative                 | 90        | 3              | 8        |           | 55         | 13        | 22        |
| primary-tumor                  | 330       | 15             | 17       | new split | 211        | 53        | 66        |
| ringnorm                       | 7400      | 2              | 20       |           | 4423       | 1127      | 1850      |
| seeds                          | 210       | 3              | 7        |           | 128        | 30        | 52        |
| semeion                        | 1593      | 10             | 256      |           | 933        | 262       | 398       |
| soybean                        | 683       | 18             | 35       | new split | 436        | 110       | 137       |
| spambase                       | 4601      | 2              | 57       |           | 2726       | 725       | 1150      |
| spect                          | 265       | 2              | 22       |           | 69         | 10        | 186       |
| spectf                         | 267       | 2              | 44       |           | 59         | 21        | 187       |
| statlog-australian-credit      | 690       | 2              | 14       |           | 412        | 106       | 172       |
| statlog-german-credit          | 1000      | 2              | 24       |           | 606        | 144       | 250       |
| statlog-heart                  | 270       | 2              | 13       |           | 165        | 38        | 67        |
| statlog-image                  | 2310      | 7              | 18       |           | 1371       | 362       | 577       |
| statlog-landsat                | 6435      | 6              | 36       |           | 3533       | 902       | 2000      |
| statlog-shuttle                | 58000     | 7              | 9        | new split | 37120      | 9280      | 11600     |
| statlog-vehicle                | 846       | 4              | 18       |           | 514        | 121       | 211       |
| steel-plates                   | 1941      | 7              | 27       |           | 1151       | 305       | 485       |
| synthetic-control              | 600       | 6              | 60       |           | 368        | 82        | 150       |
| teaching                       | 151       | 3              | 5        |           | 91         | 22        | 38        |
| thyroid                        | 7200      | 3              | 21       |           | 2993       | 779       | 3428      |
| tic-tac-toe                    | 958       | 2              | 9        |           | 573        | 146       | 239       |
| titanic                        | 2201      | 2              | 3        |           | 1296       | 355       | 550       |
| trains                         | 10        | 2              | 29       | new split | 6          | 2         | 2         |
| twonorm                        | 7400      | 2              | 20       |           | 4461       | 1089      | 1850      |
| vertebral-column-2clases       | 310       | 2              | 6        |           | 174        | 59        | 77        |
| vertebral-column-3clases       | 310       | 3              | 6        |           | 189        | 44        | 77        |
| wall-following                 | 5456      | 4              | 24       |           | 3272       | 820       | 1364      |
| waveform                       | 5000      | 3              | 21       |           | 2992       | 758       | 1250      |
| waveform-noise                 | 5000      | 3              | 40       |           | 2979       | 771       | 1250      |
| wine                           | 178       | 3              | 13       |           | 100        | 34        | 44        |
| wine-quality-red               | 1599      | 6              | 11       | new split | 1023       | 256       | 320       |
| wine-quality-white             | 4898      | 7              | 11       | new split | 3134       | 784       | 980       |
| yeast                          | 1484      | 10             | 8        | new split | 949        | 238       | 297       |
| zoo                            | 101       | 7              | 16       | new split | 64         | 16        | 21        |


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
