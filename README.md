<<<<<<< HEAD
﻿﻿﻿# AdvAudioCaptcha（Towards Improving the Security of Audio CAPTCHAs with Adversarial Examples）
=======
# AdvAudioCaptcha（Towards Improving the Security of Audio CAPTCHAs with Adversarial Examples）
>>>>>>> dfdf0dfe975f38c892a35fa8ad9d94bb049e8b71
This is the official code for the paper "Towards Improving the Security of Audio CAPTCHAs with Adversarial Examples" by Ping Wang, Haichang Gao,  Xiaoyan Guo, Zhongni Yuan and Jiawei Nian.
## Prerequisites
 - Python(3.5)
 - Tensorflow(1.13.1)
 - CUDA
 - numpy
 More details are in requirements.
 ## Install
We suggest to install the dependencies using Anaconda or Miniconda. And then install prerequisites:

    $ pip install -r requirements.txt

## How to generate adversarial audio CAPTCHAs?

<<<<<<< HEAD


![image-20220830102108465](C:\Users\cxw\AppData\Roaming\Typora\typora-user-images\image-20220830102108465.png)



**Preprocess**
=======
**Preprocess**

>>>>>>> dfdf0dfe975f38c892a35fa8ad9d94bb049e8b71
All the dataset should be:  single channel, int16, 16000Hz, wav format.

    $ python ./data/data_process_code/audio_format.py
  For reCAPTCHA v2, we need to cut out noise on both sides and pad.

    $ python ./data/data_process_code/cut_noise.py
    $ python ./data/data_process_code/padding.py
 Then, divide the dataset according to a certain proportion into train set, validation set and test set and gain the original transcription.

    $ python ./data/data_process_code/audio_getTran.py
    $ python deepSpeech_call.py
    $ python lingvo_call.py
    $ python jasper_call_new.py
    $ python w2l_call_new.py

And the length of transcriptions needs to be uniform,

<<<<<<< HEAD
    ./data/data_process_code/unify_audio_tran.py

**Train**
=======
    $ python ./data/data_process_code/unify_audio_tran.py

**Train**

>>>>>>> dfdf0dfe975f38c892a35fa8ad9d94bb049e8b71
For main experiments and ensemble training:

     $ python main_1asr.py # train only with DeepSpeech.
     $ python main_1lingvo.py # train only with Lingvo.
     $ python main_2.py # ensemble train for K=2.
     $ python main_3.py # ensemble train for K=3.
     $ python main_4.py # ensemble train for K=4.

Universal GAN:

<<<<<<< HEAD
 - main_deepspeech.py: train only with DeepSpeech.

**Test**
=======
     $ python main_deepspeech.py: train only with DeepSpeech.

**Test**

>>>>>>> dfdf0dfe975f38c892a35fa8ad9d94bb049e8b71
For main experiments and ensemble training:

    $ python advGenerate2.py # test for K=2.
    $ python advGenerate3.py # test for K=3.
    $ python advGenerate4.py # test for K=4.

Universal GAN:

    $ python main_deepspeech_test.py

 



## Contact
Please contact *** if you have any question on the codes. Enjoy!
