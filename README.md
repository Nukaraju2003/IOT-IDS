# IOT-IDS

## IoT-Intrusion-Detection-System-UNSW-NB15
### IOT Intrusion Detection based on various Machine learning and Deep learning algorithms using UNSW-NB15 Dataset


## Prerequisites
Sklearn
Pandas
Numpy
Matplotlib
Pickle

Running the Notebook
The notebook can be run on

Google Colaboratory
Jupyter Notebook

## Instructions
To run the code, user must have the required Dataset on their system or programming environment.
Upload the notebook and dataset on Jupyter Notebook or Google Colaboratory.
Click on the file with .ipynb extension to open the notebook. To run complete code at once press Ctrl + F9
To run any specific segment of code, select that code cell and press Shift+Enter or Ctrl+Shift+Enter
Caution - The code should be executed in the given order for best results without encountering any errors.

# Datasets
UNSW_NB15.csv - Original Dataset
UNSW_NB15_features.csv - 49 features with the class label. These features are described in UNSW-NB15_freatures.csv file.
bin_data.csv - CSV Dataset file for Binary Classification
multi_data.csv - CSV Dataset file for Multi-class Classification


## Deep Learning Model
Convolutional neural Networks 

## Data Preprocessing
Dataset had 45 attributes and 175341 rows.
After dropping null values Dataset had 45 attributes and 81173 rows.
Data type of attributes is converted using provided datatype information from features dataset.

### One-hot-encoding
Categorical Columns 'proto', 'service', 'state' are one-hot-encoded using pd.get_dummies() and these 3 attributes are removed afterwards.
data_cat Dataframe had 19 attributes after one-hot-encoding.
data_cat is concatenated with the main data dataframe.
Total attributes of data dataframe - 61

### Data Normalization
58 Numeric Columns of DataFrame is scaled using MinMax Scaler.
### Binary Classification
A copy of DataFrame is created for Binary Classification.
'label' attribute is classified into two categories 'normal' and 'abnormal'.
'label' is encoded using LabelEncoder(), encoded labels are saved in 'label'.
Binary dataset - 81173 rows, 61 columns

### Multi-class Classification
A copy of DataFrame is created for Multi-class Classification.
'attack_cat' attribute is classified into 9 categories 'Analysis', 'Backdoor', 'DoS', 'Exploits', 'Fuzzers', 'Generic', 'Normal', 'Reconnaissance', 'Worms'
attack_cat is encoded using LabelEncoder(), encoded labels are saved in label.
attack_cat is one-hot-encoded'.
Multi-class Dataset - 81173 rows, 69 columns
### Feature Extraction
No. of attributes of 'bin_data' - 61
No. of attributes of 'multi_data' - 69
Pearson Correlation Coefficient method is used for feature extraction.
The attributes with more than 0.3 correlation coefficient with the target attribute label were selected.
No. of attributes of 'bin_data' after feature selection - 15
'rate', 'sttl', 'sload', 'dload', 'ct_srv_src', 'ct_state_ttl', 'ct_dst_ltm', 'ct_src_dport_ltm', 'ct_dst_sport_ltm', 'ct_dst_src_ltm', 'ct_src_ltm', 'ct_srv_dst', 'state_CON', 'state_INT', 'label'
No. of attributes of 'multi_data' after feature selection - 16
'dttl', 'swin', 'dwin', 'tcprtt', 'synack', 'ackdat', 'label', 'proto_tcp', 'proto_udp', 'service_dns', 'state_CON', 'state_FIN', 'attack_cat_Analysis', 'attack_cat_DoS', 'attack_cat_Exploits', 'attack_cat_Normal'

### Splitting Dataset
Randomly Splitting the bin_data in 80% for training and 20% for testing
Randomly Splitting the multi_data in 70% for training and 30% for testing
