# Medical-Transcriptions-Classification

This Project uses data from mtsample.csv to perform medical text classification task and compare 2 model

## Model

- **BERTbase-LSTM model**
  use BERT as feature extraction to get contextualize word embedding and then pass through the LSTM model as a baseline model
- **Pubmed BERT fine tunning**
  using Pubmed BERT which training on biomedical corpus and fine tunning to predict classification

  ![image diagram](https://github.com/PRIMEADAWAS/Medical-Transcriptions-Classification/blob/main/images/diagram.png)

## Result

The BERT-LSTM model show poor performance(accuracy 19% and F1 micro 19%) because BERT was trained on wikipedia and internet text to get contextualize word embedding which does not contain medical word that is why feature extraction by BERT is not good representation literature suggest that you should you BERT model that pre-train on biomedical corpus such as Pubmed BERT and use seq classification instead of LSTM because paper show that model use Transformers as classification is better than other CNN, LSTM, biLSTM because of attention mechanism can solve problem of vanishing gradient

However, the Performance of PubMed BERT fine tunning model surpasses normal BERTbase-LSTM model show accuracy 79% and F1 micro 79% to use feature extraction from PubMed pretrain weight is better than BERT base model to represent contexual embedding and obtain sentence meaning from fine-tuning by transformer using an attention mechanism is superior to LSTM.

## Reference

- Transformer is out perform LSTM, CNN and other model  
  Lu, H., Ehwerhemuepha, L. & Rakovski, C. A comparative study on deep learning models for text classification of unstructured medical notes with various levels of class imbalance. BMC Med Res Methodol 22, 181 (2022). https://doi.org/10.1186/s12874-022-01665-y

- Biomedical text classification is domain specific that can solve by BERT model that train on biomedical corpus
  Yu Gu, Robert Tinn, Hao Cheng, Michael Lucas, Naoto Usuyama, Xiaodong Liu, Tristan Naumann, Jianfeng Gao, and Hoifung Poon. 2021. Domain-Specific Language Model Pretraining for Biomedical Natural Language Processing. ACM Trans. Comput. Healthcare 3, 1, Article 2 (January 2022), 23 pages. https://doi.org/10.1145/3458754
- Kalyan, K. S., Rajasekharan, A., & Sangeetha, S. (2021). AMMU : A Survey of Transformer-based Biomedical Pretrained Language Models. ArXiv. /abs/2105.00827
