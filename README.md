# Machine Learning Trading Bot

## Overview
In this project, we aim to enhance the trading strategies of a top financial advisory firm by incorporating machine learning algorithms. The goal is to improve the existing algorithmic trading systems to maintain a competitive edge in the market by enabling these systems to adapt to new data more effectively.

## Technologies Used
- Pandas
- NumPy
- scikit-learn
- Matplotlib
- hvPlot

## Instructions

The project is divided into the following main sections:

1. **Establish a Baseline Performance**: Utilize the provided starter code to establish a baseline for the trading algorithm.
2. **Tune the Baseline Trading Algorithm**: Adjust the model’s input features to optimize trading outcomes.
3. **Evaluate a New Machine Learning Classifier**: Apply and evaluate a second machine learning model to compare its performance.
4. **Create an Evaluation Report**: Summarize your findings and analysis.

### 1. Establish a Baseline Performance
- Import the OHLCV dataset into a Pandas DataFrame.
- Generate trading signals using short- and long-window SMA values.
- Split the data into training and testing datasets.
- Fit the SVC classifier model and review the predictions.
- Review the classification report for the SVC model predictions.
- Create a predictions DataFrame and a cumulative return plot.

### 2. Tune the Baseline Trading Algorithm
- Adjust the size of the training dataset and SMA input features.
- Document the impact of these adjustments on trading outcomes.

### 3. Evaluate a New Machine Learning Classifier
- Import a new classifier (e.g., AdaBoost, DecisionTreeClassifier, LogisticRegression).
- Fit the model with the original training data and evaluate its performance.
- Compare the new model's performance with the baseline model and the tuned trading algorithm.

### 4. Create an Evaluation Report
- Provide a comprehensive evaluation report summarizing the final conclusions and analysis.

## Results and Analysis

(Insert a summary of the baseline model performance, including any relevant PNG images of plots.)

(Describe the tuning process and its impact on the model's performance.)

(Discuss the evaluation of the new machine learning classifier, including comparisons with the baseline and tuned models.)

### Conclusions

(Provide your final analysis and conclusions based on the cumulative returns plot and classification reports. Answer the following questions:)
- Did the new model perform better or worse than the provided baseline model?
- Did the new model perform better or worse than the tuned trading algorithm?

## Future Work

(Describe potential future work and improvements that could further enhance the trading algorithm.)

---

**To Do**: Remember to adjust the specifics (like model evaluation results, specific parameters used, etc.) based on the outcomes of your project.

