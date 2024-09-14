# FTPComplEx: A Flexible Time Perspective Approach to Temporal Knowledge Graph Completion

The paper is currently under review by the journal, where it is being carefully evaluated by reviewers for its contributions, methodology, and overall quality. We are awaiting feedback and comments to further refine and improve the model based on their insights.

## Installation
Create a conda environment with pytorch and scikit-learn :
```
conda create --name tkbc_env python=3.7
source activate tkbc_env
conda install --file requirements.txt -c pytorch
```

Then install the kbc package to this environment
```
python setup.py install
```

## Datasets

To download the datasets, go to the ./tkbc/scripts folder and run:
```
chmod +x download_data.sh
./download_data.sh
```

GDELT dataset can be download [here](https://github.com/BorealisAI/de-simple/tree/master/datasets/gdelt) and rename the files without ".txt" suffix.

Once the datasets are downloaded, add them to the package data folder by running :
```
python tkbc/process_icews.py
python tkbc/process_yago.py
python tkbc/process_gdelt.py
```

This will create the files required to compute the filtered metrics.

## Reproducing results

Run the following commands in tkbc folder to reproduce the results

```
python learner.py --dataset ICEWS14 --model FTPComplEx --rank 1594 --emb_reg 1e-1 --time_reg 1e-4 --x 0.7 --y 0.8

python learner.py --dataset ICEWS05-15 --model FTPComplEx --rank 886 --emb_reg 1e-2 --time_reg 1e-2 --x 1.0 --y 0.9

python learner.py --dataset yago15k --model FTPComplEx --rank 364 --no_time_emb --emb_reg 1e-1 --time_reg 1e-4 --x 0.8 --y 0.9

python learner.py --dataset gdelt --model FTPComplEx --rank 1256 --emb_reg 1e-5 --time_reg 1e-2 --x 1.0 --y 0.9

```

## Acknowledgement
We refer to the code of [TPComplEx](https://github.com/Jinfa/TPComplEx). Thanks for their contributions.

