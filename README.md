# machine-translation-system
An open-source machine translation system using machine learning techniques.

## Disclaimer 
**This software is published for academic and non-commercial use only.

****This project is considered obsolete as the Torch framework is no longer maintained. If you are starting a new project, please use an alternative in the OpenNMT family: Translation System (TensorFlow) or Translation System (PyTorch) depending on your requirements.**

# Translation System: Open-Source Neural Machine Translation

Translation System is a full-featured, open-source (MIT) neural machine translation system utilizing the [Torch](http://torch.ch) mathematical toolkit.

<center style="padding: 40px"><img width="70%" src="http://opennmt.github.io/simple-attn.png" /></center>

The system is designed to be simple to use and easy to extend, while
maintaining efficiency and state-of-the-art translation
accuracy. Features include:

* Speed and memory optimizations for high-performance GPU training.
* Simple general-purpose interface, only requires and source/target data files.
* [C++ implementation of the translator](https://github.com/OpenNMT/CTranslate) for easy deployment.
* Extensions to allow other sequence generation tasks such as summarization and image captioning.

## Installation

OpenNMT only requires a Torch installation with few dependencies.

1. [Install Torch](http://torch.ch/docs/getting-started.html)
2. Install additional packages:

```bash
luarocks install tds
luarocks install bit32 # if using LuaJIT
```

## Quickstart

OpenNMT consists of three commands:

1) Preprocess the data.

```
th preprocess.lua -train_src data/src-train.txt -train_tgt data/tgt-train.txt -valid_src data/src-val.txt -valid_tgt data/tgt-val.txt -save_data data/demo
```

2) Train the model.

```
th train.lua -data data/demo-train.t7 -save_model model
```

3) Translate sentences.

```
th translate.lua -model model_final.t7 -src data/src-test.txt -output pred.txt
```

## Acknowledgments

Our implementation utilizes code from the following:

* [Andrej Karpathy's char-rnn repo](https://github.com/karpathy/char-rnn)
* [Wojciech Zaremba's lstm repo](https://github.com/wojzaremba/lstm)
* [Element rnn library](https://github.com/Element-Research/rnn)

## Contact
Feel free to contact us if there is any question (tech@xaindex.ai).
