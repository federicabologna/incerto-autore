# incerto-autore

Repository for the poems and code used in the experiments in Andreoni et al, *Stylometric Analysis of the Poems Attributed to an Unknown Male Author in Veronica Franco’s Terze Rime* 

_Terze rime_ (Poems in Terza Rima, 1575), a poem collection by renowned Venetian courtesan and writer Veronica Franco (1546, 1591) contains seven poems attributed to an “unknown male author”. 
We use natural language processing and supervised classification to predict the author of said poems. Due to the lack of research on early modern Italian poetry and small datasets, it is unknown what classification method work best for this task. Therefore, we test the prediction performance of 23337 models, trained with different versions of the corpus, tokenization techniques, and classification algorithms. Successively, we select the best performing models and create a voting system across models to find which poems have the highest likelihood of being authored by Veronica Franco herself.


## Repository Structure

### Code

**code** folder: contains all the Jupyter notebooks used to preprocess the poem dataset, conduct initial analyses, run classification experiments, and analyze results.

- **preparing_poems.ipynb**: Preprocesses and prepares the poem dataset for analysis

#### code/experiments
Contains notebooks for testing the performance of thousands of supervised classification models:
- **baseline_binary.ipynb**: Baseline models for binary classification (Franco vs. other)
- **classification_binary.ipynb**: Extensive binary classification experiments
- **classification_multiclass.ipynb**: Multi-class classification experiments (across all authors)
- **bert_finetune_binary.ipynb**: Fine-tuning BERT models for binary classification
- **bert_finetune_multiclass.ipynb**: Fine-tuning BERT models for multi-class classification
- **bert_predict_binary.ipynb**: BERT predictions for binary classification task
- **bert_predict_multiclass.ipynb**: BERT predictions for multi-class classification task

#### code/analysis
Contains notebooks for analyzing model predictions and generating insights:
- **general_stats.ipynb**: General statistical analysis of the poem dataset
- **summary_predictions.ipynb**: Summary analysis of model predictions across all experiments
- **summary_predictions_detail.ipynb**: Detailed breakdown of prediction results
- **prediction_binary.ipynb**: Analysis of binary classification predictions
- **prediction_multiclass.ipynb**: Analysis of multi-class classification predictions
- **prediction_multiclass_proba.ipynb**: Probability-based analysis of multi-class predictions
- **analyzing_predictions_bert.ipynb**: Specific analysis of BERT model predictions

### Data

**data/poems** folder: contains the cleaned poems in CSV format:
- **poems_split.csv**: Poems divided into 14-line chunks for granular analysis
- **poems_whole.csv**: Complete poems in their original length

### Output

**output** folder: contains results from classification experiments and model predictions

- **chunk_probabilities.csv**: Probabilities of Veronica Franco's authorship for individual poem chunks
- **classification-performance** folder: Performance metrics for all tested models
  - **binary_classification_performance.csv**: Performance results for binary classification models
  - **multi_classification_performance.csv**: Performance results for multi-class classification models
  - **binary_baseline.csv**: Baseline performance metrics
- **predictions** folder: Final predictions on the authorship of the unassigned poems
  - **predictions_binary.csv**: Binary classification predictions
  - **predictions_binary2.csv**: Updated binary classification predictions
  - **predictions_multiclass.csv**: Multi-class classification predictions
  - **predictions_multiclass2.csv**: Updated multi-class classification predictions
  - **predictions_binary_bertoldo_f1.csv**: BERT-based predictions optimized for F1 score
