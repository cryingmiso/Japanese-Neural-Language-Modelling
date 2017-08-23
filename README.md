# Japanese Neural Language Modelling(NLM) Builder
* * *
Python API to generate and KSR-test NLM in TensorFlow.

  
### Requirements
* python 2.7
* numpy 1.12.1
* MeCab 0.996
* Tensorflow-GPU 1.0.1
* grpcio 1.2.1
* mecab-python 0.996
* romkan 0.2.1


### Installation
JNLM works on Python2.7 and requires MeCab, romkan, numpy and Tensorflow serving.


1. Git clone
```sh
$ git clone https://192.168.122.28:8568/bigdata/NLM_ja_jp.git
$ cd NLM_ja_jp
$ pip install -r requirement.txt  # requirements install.
```
2. MeCab Install
```sh
$ cd ~
$ sudo apt install mecab libmecab-dev mecab-ipadic mecab-ipadic-utf8
$ wget https://pypi.python.org/packages/86/e7/bfeba61fb1c5d1ddcd92bc9b9502f99f80bf71a03429a2b31218fc2d4da2/mecab-python-0.996.tar.gz
$ tar -xvzf mecab-python-0.996.tar.gz
$ cd mecab-python-0.996
$ python setup.py build
$ python setup.py install
```
3. Requirement Install
4. Tensorflow serving Setup
.



Then you can try blstm-cws using the following command:
* Train
```sh
$ ./run_train.sh
```

* Server run
```sh
$ cd serving
$ ./run_server.sh
```

* Test
```sh
$ ./run_test.sh
```

 
### Usuage

* **run_train.sh** optional arguments:
```sh
$ vi run_train.sh
optional arguments:
  --gpuid				GPU ID (null value indicates CPU)
  --forget_bias			LSTM hyper parameter forget bias
  --keep_prob			LSTM hyper parameter keep prob
  --max_max_epoch		LSTM epoch
  --max_epoch			LSTM start of keep_prob
  --batch_size			LSTM batch size
  --hidden_size			LSTM hidden size
  --num_layers			LSTM layer
  --vocab_size			Vocab size
  --vocab			Vocab unit
  --corpus			Corpus name
  --version			Model version
  --trainfile			Train corpus file
  --validfile			Validation corpus file
  --testfile			Test corpus file
  --export_model_dir		Save path of the serving model
  --export_model_version	Serving model version
  --trained_dir			Save path of LSTM model
  --ckpt_file			Checkpoint file
```

* **run_test.sh** optional arguments:
```sh
$ vi run_test.sh
optional arguments:
  --gpuid			GPU ID (null value indicates CPU)
  --hostport			Tensowflow-serving host and port
  --modelname			Tensowflow-serving model name
  --corpus			Corpus name
  --data_path			Corpus data path
  --full_vocab			Full vocab file
  --vocab_id_to_word 		Vocab File
  --dic_hira_path		Hiragana dic path(Match)
  --dic_kata_path		Katakana dic path(Match)
  --dic_except_path		Language conversion exception dic
  --prd_file			PRD file name
  --test_file			Test file name
  --vocab_size			Vocab size
  --batch_size			LSTM batch size
  --hidden_size			LSTM hidden size
  --num_layers			LSTM layer
  --maxlen			Size of Suggest and Prediction List(character)
  --last_maxlen			Size of Suggest and Prediction List(end of word)
  --cut_jodong			Number of auxiliary verb searches
  --set_p_word			Range of auxiliary search(in prediction)

```

 
* git upload testing..
