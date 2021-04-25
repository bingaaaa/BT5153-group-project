# BT5153-group-project
Detecting Depression Users in Chinese Microblogs

## data
Data Download Link & Description.docx: Raw data link + Data description + Pre-processed Training data link

test_normal_new.csv: data of 200 normal users crawled from one weibo trending hashtag for test 1

test_depressed_new.csv: data of 200 depressed users crawled from depression supertopic for test 1

test_depressed_new2.csv: data of 100 depressed users crawled from the comments under a tree hole post on depressive order (抑郁症) supertopic for test 2

## code
Data Pre-Processing + Shallow ML + Test Result.ipynb includes data pre-processing, 7 shallow ML training and test results of XGBoost, AdaBoost, and Logistic Regression.

To run the CNN model, run CNN.ipynb with df_train.csv specified in Data Download Link & Description.docx.

EDA.ipynb includes explotory data analysis.

Xgboost Feature Importance.ipynb includes the feature importance analysis of XGBoost.

To run the BERT model, run_classifier.py should be open, and input the parameters into run configuration. 

#############Train parameters
--task_name=emlo --do_train=true --do_eval=true --data_dir=./glue --vocab_file=./uncased/vocab.txt --bert_config_file=./uncased/bert_config.json --init_checkpoint=./uncased/bert_model.ckpt --max_seq_length=128 --train_batch_size=32 --learning_rate=2e-5 --num_train_epochs=3.0 --output_dir=./tmp/emotion

##############Estimate parameters
--task_name=emlo --do_predict=true --data_dir=./glue --vocab_file=./uncased/vocab.txt --bert_config_file=./uncased/bert_config.json --init_checkpoint=./tmp/emotion/ --max_seq_length=128 --output_dir=./tmp/emotion_out

It should be noted that data should be put in the file named 'glue' and the pre-trained model should be put in the file named 'uncased' in the same file dictionary.
