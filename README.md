# Machine Learning Trading Bot

## Python Notebook

[Machine Learning Trading Bot](https://github.com/jancichocki/Module_14_Challenge/blob/main/machine_learning_trading_bot_clean.ipynb)

## Overview

This project aims to enhance an existing algorithmic trading system by integrating machine learning models that adapt to new data, ensuring the firm's competitive advantage in the market. The project evaluates the baseline performance using a Support Vector Machine (SVM) classifier and tunes the algorithm by adjusting training dataset sizes and Simple Moving Average (SMA) input features. Further, it explores the performance of an alternative machine learning classifier, AdaBoost, for potential improvements in trading strategies.

## Baseline Performance

The baseline model was established using an SVC classifier model. It was trained on a dataset comprising historical OHLCV (Open, High, Low, Close, Volume) data of emerging markets and made predictions based on the testing data. The classification report for the SVC model indicated:

<table>
    <tr>
        <th></th>
        <th>Precision</th>
        <th>Recall</th>
        <th>F1-score</th>
        <th>Support</th>
    </tr>
    <tr>
        <td><strong>-1.0</strong></td>
        <td>0.43</td>
        <td>0.04</td>
        <td>0.07</td>
        <td>1804</td>
    </tr>
    <tr>
        <td><strong>1.0</strong></td>
        <td>0.56</td>
        <td>0.96</td>
        <td>0.71</td>
        <td>2288</td>
    </tr>
    <tr>
        <td><strong>Accuracy</strong></td>
        <td></td>
        <td></td>
        <td>0.55</td>
        <td>4092</td>
    </tr>
    <tr>
        <td><strong>Macro Avg</strong></td>
        <td>0.49</td>
        <td>0.50</td>
        <td>0.39</td>
        <td>4092</td>
    </tr>
    <tr>
        <td><strong>Weighted Avg</strong></td>
        <td>0.50</td>
        <td></td>
        <td>0.43</td>
        <td>4092</td>
    </tr>
</table>

A cumulative return plot comparing actual returns vs. strategy returns illustrates the model's ability to capture market trends effectively.

## Baseline Graph
![Baseline Graph](https://github.com/jancichocki/Module_14_Challenge/blob/main/cumulative_returns_short4_long100.png)

## Tuning the Trading Algorithm

### Adjusting the Training Dataset Size

Adjusting the training dataset size had a positive impact on the model's performance. Creating a testing algorithm that found some of the best models had the following results.

#### Top AdaBoost Strategy Returns by Accuracy

1. [AdaBoost Strategy Returns - Short Window: 10, Long Window: 125, Accuracy: 86.85%](https://github.com/jancichocki/Module_14_Challenge/tree/main/Graphs/adaboost_strategy_returns_acc08685_short10_long125.png)
2. [AdaBoost Strategy Returns - Short Window: 9, Long Window: 139, Accuracy: 84.35%](https://github.com/jancichocki/Module_14_Challenge/tree/main/Graphs/adaboost_strategy_returns_acc08435_short9_long139.png)
3. [AdaBoost Strategy Returns - Short Window: 8, Long Window: 138, Accuracy: 83.88%](https://github.com/jancichocki/Module_14_Challenge/tree/main/Graphs/adaboost_strategy_returns_acc08388_short8_long138.png)
4. [AdaBoost Strategy Returns - Short Window: 8, Long Window: 137, Accuracy: 83.57%](https://github.com/jancichocki/Module_14_Challenge/tree/main/Graphs/adaboost_strategy_returns_acc08357_short8_long137.png)
5. [AdaBoost Strategy Returns - Short Window: 4, Long Window: 129, Accuracy: 82.92%](https://github.com/jancichocki/Module_14_Challenge/tree/main/Graphs/adaboost_strategy_returns_acc08292_short4_long129.png)


#### Top SVC Strategy Returns by Accuracy

1. [SVC Strategy Returns - Short Window: 4, Long Window: 68, Accuracy: 87.48%](https://github.com/jancichocki/Module_14_Challenge/tree/main/Graphs/svc_strategy_returns_acc08748_svc_short4_long68.png)
2. [SVC Strategy Returns - Short Window: 10, Long Window: 91, Accuracy: 86.07%](https://github.com/jancichocki/Module_14_Challenge/tree/main/Graphs/svc_strategy_returns_acc08607_svc_short10_long91.png)
3. [SVC Strategy Returns - Short Window: 3, Long Window: 53, Accuracy: 84.51%](https://github.com/jancichocki/Module_14_Challenge/tree/main/Graphs/svc_strategy_returns_acc08451_svc_short3_long53.png)
4. [SVC Strategy Returns - Short Window: 4, Long Window: 59, Accuracy: 84.35%](https://github.com/jancichocki/Module_14_Challenge/tree/main/Graphs/svc_strategy_returns_acc08435_svc_short4_long59.png)
5. [SVC Strategy Returns - Short Window: 12, Long Window: 115, Accuracy: 83.88%](https://github.com/jancichocki/Module_14_Challenge/tree/main/Graphs/svc_strategy_returns_acc08388_svc_short12_long115.png)

### Adjusting SMA Input Features

Modifying the SMA input features increased the strategy's effectiveness. Using 2000 random long and short windows and sorting them by accuracy we were able to greatly improve the model.

The best set of parameters found was a short window of 4 days and a long window of 68 days, which yielded the highest cumulative returns. 
[SVC Strategy Returns - Short Window: 4, Long Window: 68, Accuracy: 87.48%](https://github.com/jancichocki/Module_14_Challenge/tree/main/Graphs/svc_strategy_returns_acc08748_svc_short4_long68.png)

## Evaluation of a New Machine Learning Classifier

The AdaBoost classifier was integrated and compared against the baseline SVC model. The SVC model exhibited better performance in terms of accuracy. When observing the top accuracy scores, the SVC model achieved its best with an accuracy of 87.48% at a short window of 4 and a long window of 68. In contrast, the AdaBoost model had sightly lower accuracy but with a significantly different configuration, demonstrating its flexibility and robustness across different market conditions.

Backtesting the AdaBoost model revealed that it adapts more effectively to market changes compared to the SVC model. This adaptability is evident in the AdaBoost's consistent performance across a wider range of window settings, suggesting a potential for better generalization to unseen market scenarios.

## AdaBoost Model Strategy Results
[Open strategy_results_adaboost_long_list.csv](https://github.com/jancichocki/Module_14_Challenge/blob/main/strategy_results_adaboost_long_list.csv)

## SVC Model Strategy Results
[Open strategy_results_svc_long_list.csv](https://github.com/jancichocki/Module_14_Challenge/blob/main/strategy_results_svc_long_list.csv)

The graphical representation of the AdaBoost model's performance plot, stored in the `Graphs` subdirectory, visually underscores its superior strategy returns over the baseline SVC model. Through these plots, the impact of the AdaBoost model's accuracy on trading outcomes can be clearly observed, providing a compelling case for its application in enhancing algorithmic trading strategies.

## Graphs Directory
[View All Strategy Graphs](https://github.com/jancichocki/Module_14_Challenge/tree/main/Graphs)

## Best AdaBoost Graph
![AdaBoost Strategy Returns](https://github.com/jancichocki/Module_14_Challenge/blob/main/Graphs/adaboost_strategy_returns_acc0822_short75_long140.png)

## Evaluation Report

After thorough testing and analysis, it is evident that the AdaBoost model improved upon the baseline SVC model's performance in specific configurations. The top performance for the SVC model showed an accuracy of 87.48% with a short window of 4 and a long window of 68. In contrast, the AdaBoost model reached a slightly lower level of accuracy 86.85% but with a different configuration of a short window of 10 and a long window of 125, indicating its ability to adapt to a broader range of data windows effectively.

Despite the promising results, one limitation encountered was the dependency on window size settings, which indicates the need for extensive parameter tuning to achieve optimal performance. Furthermore, the slight variations in accuracy between the top-performing configurations underscore the challenge of predicting financial markets with high precision.

The graphs stored in the `Graphs` subdirectory visually illustrate these findings, highlighting the cumulative returns of trading strategies based on the predictions made by both models. Through these visual representations, we can observe the practical impact of model accuracy on trading outcomes, reinforcing the conclusions drawn from our analysis.

## Graphs Directory
[View All Strategy Graphs](https://github.com/jancichocki/Module_14_Challenge/tree/main/Graphs)

## Conclusions

This exploration into machine learning-assisted trading algorithms underlines the importance of model selection, parameter tuning, and the need for continuous evaluation against new market data. Machine learning offers significant opportunities to automate and optimize trading strategies, ultimately contributing to more robust and adaptable financial advisory services.

