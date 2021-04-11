# Basic Supervised NER
It is the realization of the basic supervised NER model based on bert-cased model. The model contains a BERT encoder and a linear classifier.

## Structure
- utils_ner.py
    - It contains the util function and class for data loading, specifically, it provides functions for two kinds of data types
        - `read_cluener_example_from_file`
            - for json datatype like `cluener`
        - `read_examples_from_file`
            - for standard two column data like `CONLL`, each row is "word label"
- run_ner.py
    - It is the main python script to run ner model
    - important parameters
        - data_dir: the directory where training, dev, and test data are
        - labels: the file path that contains all labels
        - model_name_or_path: backbone model to use (bert-base-cased or bert-base-chinese)
        - output_dir: the directory to output training and test result
        - sample_type: which dataloading function to use ('conll' or 'cluener')
        - max_seq_length: max length
        - num_train_epochs
        - per_gpu_train_batch_size
        - seed: global random seed
        - do_train: whether to train
        - do_eval: whether to evaluate on dev set
        - do_predict: whether to predict on test set
        - overwrite_output_dir

## Usage
- Run `pip install -r requirements`
- Refer to `run.sh` for training script. It is used to train on cluener dataset.
- Make sure you have files named `train.txt`, `dev.txt`, `test.txt` in your `data_dir` when you use CONLL dataloading function
-  Make sure you have files named `train.json`, `dev.json`, `test.json` in your `data_dir` when you use cluener dataloading function
