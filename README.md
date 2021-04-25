# BT5153-group-project
# Detecting Depression Users in Chinese Microblogs

## Data

## Code
Data Pre-Processing + Shallow ML + Test Result.ipynb
CNN.ipynb
BERT.py
EDA.ipynb
Xgboost Feature Importance.ipynb

To run the BERT model, run_classifier.py should be open, and input the parameters into run configuration. 

#############Train parameters
--task_name=emlo --do_train=true --do_eval=true --data_dir=./glue --vocab_file=./uncased/vocab.txt --bert_config_file=./uncased/bert_config.json --init_checkpoint=./uncased/bert_model.ckpt --max_seq_length=128 --train_batch_size=32 --learning_rate=2e-5 --num_train_epochs=3.0 --output_dir=./tmp/emotion

##############Estimate parameters
--task_name=emlo --do_predict=true --data_dir=./glue --vocab_file=./uncased/vocab.txt --bert_config_file=./uncased/bert_config.json --init_checkpoint=./tmp/emotion/ --max_seq_length=128 --output_dir=./tmp/emotion_out

It should be noted that data should be put in the file named 'glue' and the pre-trained model should be put in the file named 'uncased' in the same file dictionary.
