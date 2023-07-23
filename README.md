# RUL_Prediction
Remaining Useful Life (RUL) is an estimate of remaining time that a machine or a system or a mechanical element is able to function according to it's expected purpose before calling for replacement.

Remaining Useful Life (RUL) Prediction makes use of prediction methods or prediction models to predict the future performance of a machine and to obtain the available time left for a machine to work properly without causing failure.

# Publication on Remaining Useful Life Prediction of Mechanical Bearings using Convolution Neural Network and Long Short Term Memory
This research article focuses on predicting the Remaining Useful Life (RUL) of Mechanical Bearings. I along with my teammate developed a data-driven methodology that incorporates Continuous Wavelet Transform (CWT), Convolution Neural Network (CNN), and Long Short-Term Memory (LSTM) Network for Remaining Useful Life (RUL) prediction. Below attached the research paper link for reference.

https://drive.google.com/file/d/1EAF9X1G1OkosFdy-HWeAKGP06QoepIAz/view

# About the collected dataset
The collected dataset is the PRONOSTIA Bearings Dataset (PHM IEEE 2012 Data Challenge Dataset). The collected dataset consists of 6 bearings learning or training datasets. The below learning dataset links are taken from wkzs111 GitHub repository (https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset).

Bearing1_1 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Learning_set/Bearing1_1

Bearing1_2 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Learning_set/Bearing1_2

Bearing2_1 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Learning_set/Bearing2_1

Bearing2_2 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Learning_set/Bearing2_2

Bearing3_1 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Learning_set/Bearing3_1

Bearing3_2 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Learning_set/Bearing3_2

The dataset also contains 11 bearings test datasets. The below test dataset links are taken from wkzs111 GitHub repository (https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset).

Bearing1_3 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Test_set/Bearing1_3

Bearing1_4 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Test_set/Bearing1_4

Bearing1_5 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Test_set/Bearing1_5

Bearing1_6 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Test_set/Bearing1_6

Bearing1_7 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Test_set/Bearing1_7

Bearing2_3 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Test_set/Bearing2_3

Bearing2_4 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Test_set/Bearing2_4

Bearing2_5 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Test_set/Bearing2_5

Bearing2_6 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Test_set/Bearing2_6

Bearing2_7 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Test_set/Bearing2_7

Bearing3_3 - https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/tree/master/Test_set/Bearing3_3

The datasets are run-to-failure experiments. Run-to-failure experiment means at first (at starting point) the bearings will be in healthy condition and eventually fails when progressing in time. In the dataset, for every 10 seconds, vibration signals are recorded for 0.1 seconds. The recorded signals are 1D raw vibration signals and these vibration signals are present only in time domain, contains only time domain information. Every data file present in datasets contains 2560 data points (horizontal and vertical acceleration vibration data points). The pronostia data is the time-series data. (Time-series data is a set of observations (data) usually collected at discrete and equally spaced time intervals). Here in the dataset, vibration signals are recorded at every 10 seconds (equal time intervals). Refer below link to understand more about the PRONOSTIA dataset - IEEE PHM 2012 Prognostic challenge.

https://github.com/wkzs111/phm-ieee-2012-data-challenge-dataset/blob/master/IEEEPHM2012-Challenge-Details.pdf

# Implementation
(1) Storing data into pickle files (data_pkz.ipynb)

Converted all the files of learning data set directories (Bearing1_1, Bearing1_2, Bearing2_1, Bearing2_2, Bearing3_1, Bearing3_2) into single combined pickle(.pkz) files(bearing1_1.pkz, bearing1_2.pkz, bearing2_1.pkz, bearing2_2.pkz, bearing3_1.pkz, bearing3_2.pkz) for easy data access and faster data retrieval.

https://colab.research.google.com/drive/1KvPmQW-W0mrVwE8FFI2iHKwOs0llA8l5

(2) Data Preprocessing and Signal Processing (DP_SP.ipynb)

Applied CWT on 1D signals and converted into normalized 2D features.

https://colab.research.google.com/drive/1Vs6lfdhlK6wzIarCcm3Zh73FmPu0RIXA#scrollTo=jhvMoEJYKmiF

(3) Dataset and DataLoader for PyTorch (torch_Dataset_DataLoader.ipynb)

PyTorch (or Torch) Dataset and DataLoader are used for easy accessing (retrieving, obtaining, acquiring, reading, examining) of data for machine learning and deep learning models. A lot of effort in solving any machine learning problem goes into preparing (preprocessing) the data. PyTorch provides many tools to make data loading (activation) easy (if data loading is easy, feeding the data into the model is easy), and to make the code more readable.

DataLoader provides randomization for loading data during model training.

https://colab.research.google.com/drive/14t8-k-jCs6fgiYYoHyEPeWb5rzUVv1m8#scrollTo=LlF8Xr3XmRuM

(4) CNN model training (CNN_Model_Train.ipynb)

Training CNN Model for fault probability prediction using PyTorch framework and validating or evaluating the model performance on all 6 learning datasets.

https://colab.research.google.com/drive/1R-KQ6qK-R3x-0x8FjKrxbAENEqJzK1Xt#scrollTo=NaYgBdJYYYOt

(5) Packing data into sequences for CNN + LSTM model (CNN+LSTM_Dataset_Preparation.ipynb)

LSTM expects data in sequences, so contiguous sequences from original data are packed together and loaded using torch Dataset and DataLoader.

https://colab.research.google.com/drive/1a3dgJUOI3aa1ruHrPbFKs34sGxGKfWj5?authuser=0#scrollTo=4wiBn8-9gwHX

(6) CNN + LSTM model training (CNN+LSTM_Model_Train.ipynb)

Training CNN + LSTM Model for fault probability prediction using PyTorch framework and validating or evaluating the model performance on all 6 learning datasets.

https://colab.research.google.com/drive/10xwxceiUf5CwS8E9AWaozT0SyTjr4Hvf#scrollTo=FanPNsTNvSnt

(7) Storing test data in pickle files (Test_Data_pkz.ipynb)

Converted all the files of test data set directories (Bearing1_3, Bearing1_4, Bearing1_5, Bearing1_6, Bearing1_7, Bearing2_3, Bearing2_4, Bearing2_5, Bearing2_6, Bearing2_7, Bearing3_3) into single combined pickle(.pkz) files(bearing1_3.pkz, bearing1_4.pkz, bearing1_5.pkz, bearing1_6.pkz, bearing1_7.pkz, bearing2_3.pkz, bearing2_4.pkz, bearing2_5.pkz, bearing2_6.pkz, bearing2_7.pkz, bearing3_3.pkz) for easy data access and faster data retrieval.

https://colab.research.google.com/drive/1Ka1xQjLUdWfvkB3fFIR3n6ea3meV3XH2?authuser=1

(8) Data Preprocessing and Signal Processing on test data (Test_Dataset_Preparation.ipynb)

Applied CWT on 1D signals and converted into normalized 2D features.

https://colab.research.google.com/drive/1FEEby_GCyEBaR9qA1JdBSDU9NmfMg0fP#scrollTo=Ut7FZ1Wk1gRK

(9) CNN + LSTM Model on test data (CNN+LSTM_Model_on_Test_data.ipynb)

Load 2D test data features into trained CNN + LSTM model using PyTorch Dataset and DataLoader. 

https://colab.research.google.com/drive/1kqhX3O8vl-8OstRhXhu0HvHTbzzNvZLT?authuser=1#scrollTo=l7Ic5vJEQgNC

