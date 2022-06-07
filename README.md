# Implementation of "An Improved Pretraining Strategy-Based Scene Classification With Deep Learning" (Zongli Chen et al.)

## Getting started

1. Download the following datasets:
- NWPU-RESISC45
- PatternNet
- RSI-CB
- UCM
- AID

2. Merge the datasets NWPU-RESISC45, PatternNet and RSI-CB in a single folder to create the HRRS dataset

3. Run the following command to install the dependecies:

```
pip install -r requirements.txt
```

4. Run the notebook **create_tfrecords** to create the tfrecords files for the 3 datasets (HRRS, UCM and AID)

5. Run the notebook **pretrain_HRRS** to pretrain the backbone model

6. Run the notebook **train_AID_UCM** to fine-tune the model in the AID and UCM datasets

## Results

Results for 5 runs of 80/20 train/test split with batch size = 64 (authors used 256):

| Model | Dataset | Accuracy (%) | Kappa |
| - | - | - | - |
| Paper | AID | 94.30±0.67 | 0.94±0.01 |
| Paper | UCM | 98.81±0.76 | 0.98±0.01 |
| Mine + SGD  | AID | 90.42±0.10 | 0.90±0.001 |
| Mine + SGD  | UCM | 90.55±2.8  | 0.90±0.029 |
| Mine + Adam | UCM | 95.77±0.84 | 0.96±0.01 |
| Mine + Adam | AID | 93.38±0.2662 | 0.93±0.003 |