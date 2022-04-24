abortion_news_analysis
Roderick Li and Jasmijn Cnossen
December 2021

In this project, we investigated the semantics and the style used by English and Dutch news sources to write articles about abortion. We analyzed the differences between different sources in what words were used and in the readability of the articles.

Here you can find our blog post: add link

In this repository, you will find the following files and folders:
●	annotations: folder containing all English (eng) and Dutch (nld) annotation sheets, as well as the annotation guidelines.
●	data: folder containing all English and Dutch articles in tsv files: eng/abortion_overview_clean.tsv and nld/abortus_overview_clean.tsv. In addition, the folder contains databases on word feature ratings: mrc2.dct.txt for English words, and AoA.xlsx and concreteness.xlsx for Dutch words.
●	get_all_documents.py: script that extracts the datasets.
●	evaluate_annotation.py: script that outputs the inter-annotator agreement.
●	run_all_analyses.py: script that runs all analyses and outputs the results.

Before running the run_all_analyses.py, download the models as specified in the requirements.txt and put them in the data folder. Furthermore, obtain a Media Stack API key as specified in the requirements.txt and fill it in at the beginning of the code behind “API_key = “.

Beware that the run_all_analyses.py takes a long time to run due to the language models that have to load.

Note: the get_all_documents.py does not give the exact same dataset as the ones in the data folder. Even though we did specify the dates when scraping with the Media Stack API, it does not give the exact same output as we got earlier. This would lead to different analysis results if the output of get_all_documents.py is used as the dataset. Therefore, in the script run_all_analyses.py our original dataset is used.

##Models to download
To get the word embeddings in run_all_analyses.py, our code uses two pretrained models that can be downloaded from the Internet. The model names and their external links are as follows:
●	English: "wiki-news-300d-1M.vec" (downloaded at https://fasttext.cc/docs/en/english-vectors.html)
●	Dutch: "cc.nl.300.vec" (downloaded at https://fasttext.cc/docs/en/crawl-vectors.html)
Please make sure the models are put in the correct directory (data folder) and unpack them in order to run this script.

##API Access Key

In order to use the Media Stack API, you’ll need to sign up for a mediastack account and get the access key (https://mediastack.com/documentation). Putting the access key in the code, you’ll be able to crawl news articles.
