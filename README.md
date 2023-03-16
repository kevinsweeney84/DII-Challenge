# DII-Challenge-2019

The early identification of sepsis cases.

## build the env

```shell
pip install -r requirement.txt
```

## data preprocessing

- create result folder for data preprocessing results

```shell
mkdir result
mkdir data
mkdir data/models
```

- generate json files

```shell
cd preprocessing
python gen_master_feature.py --master-file ../file/master.csv
# only for task1
python gen_feature_time.py --vital-file ../file/vital.csv

python gen_vital_feature.py --vital-file ../file/vital.csv
python gen_label_feature.py --label-file ../file/label.csv

# train and validate the model, the best model will saved in ../data/models/

# for task1 case1
python main.py --task case1
# for task1 case2
python main.py --task task1
# for task2
python main.py --task task2

# You can also run the code by:

python run.py --label-file ../file/label.csv --vital-file ../file/vital.csv --master-file  ../master.csv --task case1

```
