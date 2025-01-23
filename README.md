# incerto-autore

Repository for the poems and code used in the experiments in Andreoni et al, *Stylometric Identification of the “Unknown Male Author” in Veronica Franco’s Terze rime.* 

_Terze rime_ (Poems in Terza Rima, 1575), a poem collection by renowned Venetian courtesan and writer Veronica Franco (1546, 1591) contains seven poems attributed to an “unknown male author”. 
We use natural language processing and supervised classification to predict the author of said poems. Due to the lack of research on early modern Italian poetry and small datasets, it is unknown what classification method work best for this task. Therefore, we test the prediction performance of 23337 models, trained with different versions of the corpus, tokenization techniques, and classification algorithms. Successively, we select the best performing models and create a voting system across models to find which poems have the highest likelihood of being authored by Veronica Franco herself.


**code** folder: contains all the jupyter notebooks used to preprocess the poem dataset, do an initial analysis of the dataset, conduct classification experiments, and analyze the results of the classification. <br>
- **experiments** folder: contains code to test the performance of thousands of supervised classification models on the prediction task. <br>
- **analysis** folder:

**data/poems** folders: contains the cleaned poems in CSV files: <br>
- "poems_split.csv" contains the poems split in 14 line chunks; <br>
- while the "poems_whole.csv" contains the poems in their original length.

**output** folder: contains the CSV files with information on the best performing models and the **predictions** folder contains the predictions resulting from these models on who might be the author of the unassigned poems.
