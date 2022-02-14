# Kaggle Jigsaw Rate Severity of Toxic Comments 7th place solution (mst8823 part)
- This is the repository of [mst8823](https://www.kaggle.com/mst8823) part in the 7th place solution of [Jigsaw Rate Severity of Toxic Comments](https://www.kaggle.com/c/jigsaw-toxic-severity-rating/).
- The discription of this solution is available [here](https://www.kaggle.com/c/jigsaw-toxic-severity-rating/discussion/306366).
- The inference notebook in the competition is available [here](https://www.kaggle.com/columbia2131/jigsaw-team-ensemble-006-fix/notebook).

# Hardware
I used 2 different machines.
1. Google Colaboratory(Colab) Pro+
2. Kaggle notebook

# Environment(Google Colab Pro+)
1. Please set your kaggle 
2. Replace `author`, `colab_dir`, `drive_path`, and `api_path` in the `Config` of each notebook in the Notebooks folder with your choice.
3. The directory structure is assumed to be as follows.
```
{colab_dir}
    └── {author}
        ├── Input
        ├── Notebooks
        └── kaggle_api_token.json
```
4. If the run is successful, the `Output` and `Submission` folders will be created dynamically, and the trained weights, prediction results, and csv files for submission will be stored.


# Data
- Jigsaw Rate Severity of Toxic Comments
  - Please download data to ./Input/jigsaw-toxic-severity-rating from https://www.kaggle.com/c/jigsaw-toxic-severity-rating/data and unzip it. (If you have set an api token, the data will be downloaded and unzipped automatically)

 - Please download jigsaw-toxic-comment-classification-challenge/PseudoLabelDataset.csv to ./Input/PuseudoLabelingJigsaw from https://www.kaggle.com/columbia2131/puseudolabelingjigsaw.


# Model download
I used 2 pretrained models that are publicly available in [Hugging Face](https://huggingface.co/). 
- multilingual-toxic-xlm-roberta: https://huggingface.co/unitary/multilingual-toxic-xlm-roberta


# Preprocess
We built models based on "validation_data.csv" provided in this competition, and then inferred the text of "Toxic Comment Classification Challenge", "[ruddit jigsaw dataset](https://www.kaggle.com/rajkumarl/ruddit-jigsaw-dataset)", and "[Toxic Tweets Dataset](https://www.kaggle.com/ashwiniyer176/toxic-tweets-dataset)", and used the results as training data to build a new model. (Pseudo labeling)

- Models built based on "validation_data.csv": https://www.kaggle.com/columbia2131/jigsaw-exp019-toxic-xlm-roberta
All pseudo labeling dataset: https://www.kaggle.com/columbia2131/puseudolabelingjigsaw

# Train
- Two models(Exp-029-toxic-xlm-roberta-Pseudo-Ruddit, Exp-030-toxic-xlm-roberta-Pseudo-Jigsaw) were trained 5fold on Google Colab Pro+ (GPU:V100). 
- One model(pseudo-labeling-001-code-fit) was trained 5 fold on Kaggle Code (GPU:P100)
