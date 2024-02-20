# sep-dataset

This repository releases the dataset for "Learning to Generate Explainable Stock Predictions using Self-Reflective Large Language Models" [[Paper](https://arxiv.org/abs/2402.03659)].

Note: For text data, only the **raw** dataset is used in our work. The **preprocessed** dataset was used to conduct ablation studies with existing models.

## Dataset Overview
Price and tweet data from 2020 to 2022 of 55 stocks, coming from the top 5 stocks in 11 industries.

The full list of stocks and their companies can be found in **stocktable.pdf**.

## Data Components
This dataset comprises two main components,

* **./tweet**: Tweet data from [Twitter](https://twitter.com/)
* **./price**: Price data from [Yahoo Finance](http://finance.yahoo.com/)

## Data Format
We collect data in the same format as the [Stocknet Dataset](https://github.com/yumoxu/stocknet-dataset).

As the number of tweets have increased exponentially, we also employed a clustering pipeline to obtain the most representative tweets for each day.

### Raw Tweet Data
Format: JSON  
Keys: see [Introduction to Tweet JSON](https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/intro-to-tweet-json)

### Preprocessed Tweet Data
Format: JSON  
Keys: 'text', 'created\_at', 'user\_id\_str'

### Raw Price Data
Format: CSV  
Entries: date, open price, high price, low price, close price, adjusted close price, volume  

### Preprocessed Price Data
Format: TXT  
Entries: date, close price, open price, high price, low price, close price change, volume  
Note: *open, high, low, close prices are normalized with the last close price,* $p\_t = {\tilde{p}\_t / \tilde{p}^c\_{t-1}}-1$.

## Citation
If you use this dataset, please cite our paper.

```
@inproceedings{koa2024learning,
  title={Learning to Generate Explainable Stock Predictions using Self-Reflective Large Language Models},
  author={Koa, Kelvin JL and Ma, Yunshan and Ng, Ritchie and Chua, Tat-Seng},
  booktitle={Proceedings of the ACM Web Conference 2024},
  year={2024}
}
```
