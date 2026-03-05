# Phishing_ML_Project
> Authors: Ishmael Kwayisi and Chelsea Alysson Ongjoco

An empirical study on phishing URL detection using lexical feature engineering and binary classification models, analyzing performance metrics and decision threshold tradeoffs.

## Research Objective

Phishing attacks frequently rely on deceptive URLs to trick users into visiting malicious websites. This project investigates whether simple lexical features extracted from URLs can be used to accurately classify phishing websites.

The research focuses on:

• Identifying which URL features are most predictive of phishing behavior  
• Evaluating the performance of a logistic regression classifier  
• Exploring the tradeoff between security and false positives when adjusting classification thresholds

## Dataset

The dataset used in this project is comprised of labeled URLs that are classified as either phishing or legitimate. 

Each URL is represented by a set of lexical features extracted by the URL string.  

Dependent Variables:

phishing → 1 = phishing 
phishing → 0 = legitimate

Work Cited: Harshit Goswami, Tanmay Jha, Chirag Solanki, Dushyant Nagal, Vibhu Yadav, Arvind Prasad (2025). StealthPhisher Phishing Attack Dataset. IEEE Dataport. https://dx.doi.org/10.21227/f1q1-at18

## Features Used in the Model

The following lexical features were selected for the classification model:

- DomainLengthOfURL
- URLComplexity
- CharacterComplexity
- TLDLength
- LetterCntInURL
- IsDomainIP
- URLLength (Initially)
- HyphenCount (Initially)

Features such as URL length and hyphen count were excluded because they did not appear to provide strong discriminatory power.

## Methodology

The classification model was built using logistic regression.

Steps in the workflow:

1. Load dataset
2. Select relevant lexical features
3. Split data into training and testing sets
4. Train logistic regression classifier
5. Evaluate model performance
6. Adjust classification threshold to analyze security tradeoffs

Libraries used:

- pandas
- scikit-learn
- matplotlib
- seaborn

## Model Evaluation

Model performance was evaluated using:

- Accuracy
- Recall
- F1-Score
- ROC Curve
- AUC score

## Results

Four model configurations were tested to evaluate the impact of feautre selection and classification threshold on phishing detection performance. 

Experiments varied: 
* Inclusion of HTTPS feature
* Classification threshold used for prediction

| Model | HTTPS Feature | Threshold | Accuracy | Recall | AUC |
|------|---------------|-----------|----------|--------|-----|
| Model 1 | Included | 0.50 | 0.87 | 0.79 | 0.92 |
| Model 2 | Included | 0.70 | 0.86 | 0.83 | 0.92 |
| Model 3 | Removed | 0.50 | 0.80 | 0.69 | 0.85 |
| Model 4 | Removed | 0.70 | 0.81 | 0.78 | 0.85 |

## Reproducing The Experiment

1.Clone the repository:
https://github.com/IshKwayisi1232004/Phishing_ML_Project.git

2. Install dependencies:
pip install -r requirements.txt

3. Launch JupyterLab:
python -m jupyterLab

4. Open and run: 
notebooks/Phishing_Analysis.ipynb

## Future Work

- Expanding the feature set
- Using a deep learning model
- Investigating real-time phishing app

## Refereces
StealthPhisher Phishing Attack Dataset -  https://ieee-dataport.org/documents/stealthphisher-phishing-attack-dataset