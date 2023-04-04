# Call for Customized Conversation: Customized Conversation Grounding Persona and Knowledge

Source codes for the baseline models of **[Call for Customized Conversation: Customized Conversation Grounding Persona and Knowledge](https://arxiv.org/abs/2112.08619)**, accepted at [AAAI-22](https://aaai.org/Conferences/AAAI-22/).



### Environment Setting
We trained the models under the setting of `python==3.7` and `torch==1.5.0`,  with one RTX8000 GPU. Also, our codes are built on the codes of [huggingface](https://github.com/huggingface/transfer-learning-conv-ai), and we utilized [pytorch-ignite](https://github.com/pytorch/ignite) from pytorch in [`ignite`](https://github.com/pkchat-focus/FoCus/tree/main/ignite) folder.

1.Make a virtual environment
    
    $conda create -n ENV_NAME python=3.7

2.Install `pytorch==1.5.0`

    $conda install pytorch==1.5.0 torchvision==0.6.0 cudatoolkit=10.2 -c pytorch

3.Install the required libraries.
    
    $pip install -r requirements.txt
    


### Dataset [**[FoCus dataset v2](https://drive.google.com/file/d/1YmEW12HqjAjlEfZ05g8VLRux8kyUjdcI/view?usp=sharing)**]
This data is the modified version of the original data (which is reported in the paper) after ethical inspection.

| FoCus v2 STATISTICS | Train | Valid |
| --- | --- | --- |
| `# dialogues` | 12,484 | 1,000 |
| `# avg rounds` | 5.63 | 5.64 |
| `# knowledge-only answers` | 37,488 | 3,007 |
| `# persona-knowledge answers` | 32,855 | 2,630 |
| `# landmarks` | 5,152 | 923 |
| `avg len of Human's utterances` | 40.70 | 40.21 |
| `avg len of Machine's utterances` | 138.16 | 138.60 |

You should create directories named **`infer_log_focus`, `train_log_focus`, `test_log_focus`, `models`, `data`** under FoCus folder.

We put train, valid, test files of the dataset in the **`data`** folder. (The test set will be available after March 2022.)

The project directory should follow this directory structure:


    📦FoCus
    ┣ 📂data
    ┃ ┗ 📜train.json
    ┃ ┗ 📜valid.json
    ┣ 📂ignite
    ┣ 📂infer_log_focus
    ┣ 📂models
    ┣ 📂python_tf_idf
    ┣ 📂test_log_focus
    ┣ 📂train_log_focus
    ┣ 📜classification_modules.py
    ┣ 📜data_utils.py
    ┣ 📜evaluate_test.py
    ┣ 📜evaluate_test_ppl.py
    ┣ 📜inference.sh
    ┣ 📜inference_test.py
    ┣ 📜LICENSE
    ┣ 📜README.md
    ┣ 📜requirements.txt
    ┣ 📜test.sh
    ┣ 📜train.sh
    ┣ 📜train_focus.py
    ┗ 📜utils_focus


### Training the models
Uncomment the command lines in the **`train.sh`** file, to start training the model. 

    $ sh train.sh 


### Evaluation
Uncomment the command lines in the **`test.sh`** file, to evaluate the model on the test set. 

    $ sh test.sh


### Inference
Uncomment the command lines in the **`inference.sh`** file, to generate utterances with the trained models.

    $ sh inference.sh


### Our Workshop @ [COLING 2022](https://coling2022.org/)
We are going to hold **[the 1st workshop on Customized Chat Grounding Persona and Knowledge](https://sites.google.com/view/persona-knowledge-workshop)** in Octorber 2022.


### Citation
To use our data or source code, please cite our paper:

    @inproceedings{jang2022call,
      title={Call for Customized Conversation: Customized Conversation Grounding Persona and Knowledge},
      author={Jang, Yoonna and Lim, Jungwoo and Hur, Yuna and Oh, Dongsuk and Son, Suhyune and Lee, Yeonsoo and Shin, Donghoon and Kim, Seungryong and Lim, Heuiseok},
      booktitle={Proceedings of the AAAI Conference on Artificial Intelligence},
      volume={36},
      number={10},
      pages={10803--10812},
      year={2022}
    }

Written by [Yoonna Jang](https://github.com/YOONNAJANG).


(c) 2021 [NCSOFT Corporation](https://kr.ncsoft.com/en/index.do) & [Korea University](http://blp.korea.ac.kr/). All rights reserved.
