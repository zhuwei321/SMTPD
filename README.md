# **SMTPD：A New Benchmark for Temporal Prediction of Social Media Popularity** 

<img src="https://github.com/zhuwei321/SMTPD/blob/main/images/model.jpg" style="zoom: 15%;" />

## About

​     Targeting to fix up the above shortcomings of existed datasets, we propose a new benchmark called Social Media Temporal Popularity Dataset (**SMTPD**) by observing multi-modal content from mainstream for cutting-edge research in the field of social multimedia along with multi-modal feature temporal prediction. 
Multi-modal contents of social media posts in multiple languages generated the daily popularity information during the communication process. We define such a post as a sample of SMTPD, and
propose a multi-modal framework as a baseline to achieve the temporal prediction of popularity scores. The proposed framework consists of two parts, feature extraction and regression. In the feature extraction part, multiple pre-training models and pre-processing methods are introduced to translate the multi-modal content into deep features. In the regression part, we encode the state and time sequence of the extracted features, and adopt the LSTM-based structure to regress the 30-day popularities. Through analysis and experiments, we discover the importance of early popularity to the task of popularity prediction, and demonstrate the effectiveness of our method in temporal prediction. Generally, the contribution of this work can be summarized as:

-  Against the missing of temporal information in social media popularity researches, we observe over 282K multilingual samples from mainstream social media since they released on the network lasting for 30 days. We refer to these samples as SMTPD, a new benchmark for temporal popularity prediction.
- item Basing on existed methods, we innovate in both the selection of feature extractors and the construction of the temporal regression component, and suggest a baseline model which enables temporal popularity prediction to be conducted across multiple languages while aligning prediction times.
- Exploring the popularity distribution and the correlation between popularity at different times. Based on these, We find the importance of early popularity for popularity prediction task, and point out that the key-point for predicting popularity is to accurately predict the early popularity.

Paper link: https://arxiv.org/abs/2503.04446

## How to use？

1. Use git command to pull the project code:

   ```
   gh repo clone zhuwei321/SMTPD
   ```

2. Download the dataset called basic_view_pn.csv and the video cover image compression package called img_yt.zip, unzip them and save them in the data_source folder.
    The  google driver download disk link is:

  ```
  https://drive.google.com/drive/folders/1PmUrmfCAyH-jzUP-BSk0KeEpx19nOaBM?usp=sharing
  ```

​        And downloaded baidu cloud download disk link is：

```
https://pan.baidu.com/s/1Uc9qv8O_1_Juh1xcf7hsdg?pwd=j8e2 
extract code: j8e2
```

​       Download the  volume to the same directory and decompress it.

3. Set the file path of the dataset in the parser of main.py in the project code，and in smp_model.py,   youtube_lstm3 is the model mentioned in our paper, and the paths of bert_model and token need to be set by yourself. In youtube_data_lstm in smp_data.py, set whether to use EP and the number of days you want to predict. **Note that the seq_len here needs to be consistent with the seq_len in main.py.**Then you can run this project:

```
nohup python main.py --train=True --K=0 > output.log 2>&1 &
```

If you want to test a trained model, please set the path of model in main.py. Then run:

```
python main.py --test=True --K=0 
```

## For the improved framework HARP for the journal's extended version, please visit: https://github.com/zhuwei321/HARP
