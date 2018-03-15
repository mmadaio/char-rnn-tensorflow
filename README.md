char-rnn-tensorflow
===

[![Join the chat at https://gitter.im/char-rnn-tensorflow/Lobby](https://badges.gitter.im/char-rnn-tensorflow/Lobby.svg)](https://gitter.im/char-rnn-tensorflow/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Coverage Status](https://coveralls.io/repos/github/sherjilozair/char-rnn-tensorflow/badge.svg)](https://coveralls.io/github/sherjilozair/char-rnn-tensorflow)
[![Build Status](https://travis-ci.org/sherjilozair/char-rnn-tensorflow.svg?branch=master)](https://travis-ci.org/sherjilozair/char-rnn-tensorflow)

Multi-layer Recurrent Neural Networks (LSTM, RNN) for character-level language models in Python using Tensorflow.

Inspired from Andrej Karpathy's [char-rnn](https://github.com/karpathy/char-rnn).

## Requirements
- [Tensorflow 1.0](http://www.tensorflow.org)

## Setup:

### In a terminal window:
	
- If you don’t have pip, then install pip first:
		sudo apt-get install python3-pip

- If you don’t have virtualenv, then:
		pip install virtualenv

- If you haven’t set up your virtual environment yet
 - Set up virtualenv (venv) within the char-rnn directory:
  - cd to the directory
  - virtualenv venv 

### Every time:

In your directory,
- Activate virtualenv with:
	source venv/bin/activate

- Run with:
	python train.py

- To train on new text:
	python train.py --data_dir=./data/name-of-new-folder

- To view output graphs and logs on “TensorBoard”:
- - In separate terminal window:
	cd to directory
 	tensorboard --logdir=./logs/
	Open a browser to http://localhost:6006 or the correct IP/Port 			specified.

- To generate new text:
	In separate terminal window:
		cd to directory
			python sample.py 

## Best model:
- rnn-size: 128
- learning_rate: 0.008
- dropout: 0.5
- seq = 50
	

- Next: check # of parameters vs. data size, then tune rnn_size and dropout rate accordingly 

===

## Basic Usage
To train with default parameters on the tinyshakespeare corpus, run `python train.py`. To access all the parameters use `python train.py --help`.

To sample from a checkpointed model, `python sample.py`.

## Datasets
You can use any plain text file as input. For example you could download [The complete Sherlock Holmes](https://sherlock-holm.es/ascii/) as such:

```bash
cd data
mkdir sherlock
cd sherlock
wget https://sherlock-holm.es/stories/plain-text/cnus.txt
mv cnus.txt input.txt
```

Then start train from the top level directory using `python train.py --data_dir=./data/sherlock/`

A quick tip to concatenate many small disparate `.txt` files into one large training file: `ls *.txt | xargs -L 1 cat >> input.txt`

## Tensorboard
To visualize training progress, model graphs, and internal state histograms:  fire up Tensorboard and point it at your `log_dir`.  E.g.:
```bash
$ tensorboard --logdir=./logs/
```

Then open a browser to [http://localhost:6006](http://localhost:6006) or the correct IP/Port specified.


## Roadmap
- [ ] Add explanatory comments
- [ ] Expose more command-line arguments
- [ ] Compare accuracy and performance with char-rnn
- [ ] More Tensorboard instrumentation

## Contributing
Please feel free to:
* Leave feedback in the issues
* Open a Pull Request
* Join the [gittr chat](https://gitter.im/char-rnn-tensorflow/Lobby)
* Share your success stories and data sets!
