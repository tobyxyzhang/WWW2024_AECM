## WWW2024_AECM
### Adversarial-Enhanced Causal Multi-Task Framework for Debiasing Post-Click Conversion Rate Estimation

### 1. Abstract

In real-world industrial scenarios, post-click conversion rate (CVR) prediction models are trained offline based on click events and subsequently applied online to both clicked and unclicked events. Unfortunately, unclicked events are inevitably difficult to estimate due to user self-selection, which leads to a degradation of CVR prediction accuracy. In order to estimate the prediction of unclicked events, the current mainstream Doubly Robust (DR) estimators introduce the concept of imputed errors. However, inaccuracies in imputed errors can increase the uncertainty in the generalization bound of CVR predictions, consequently resulting in a decline in the CVR prediction accuracy. To challenge this issue, we first present a theoretical analysis of the bias and variance inherent in DR estimators and then introduce a novel causal estimator that seeks to strike a balance between bias and variance within the DR framework, thus optimizing the learning of the imputation model in a more robust manner. Additionally, drawing inspiration from adversarial learning techniques, we propose a novel dual adversarial component, which learns from both the space level and the task level to eliminate the causal influence of input features on the CTR task (i.e., the click propensity), with the goal of achieving unbiased estimations. Our extensive experimental evaluations, conducted on both the widely used benchmark and the real-world large-scale Internet giant platform, convincingly demonstrate the effectiveness of our proposed scheme. Besides, we have released a high-quality industrial dataset named **Tenc-UnionAds** used for selection bias research in the advertising field.

<img src="https://github.com/tobyxyzhang/WWW2024_AECM/blob/main/PNGs/AECM.png?raw=true" width = "550" height = "300" alt="图片名称" align=center />



### 2. Dataset

Tencent Advertising is an advertising platform under Tencent Corporation, providing advertising placement and marketing solutions for advertisers and brands. With a vast user base and diverse product ecosystem, Tencent offers a wide range of advertising display and promotion channels to advertisers.

The Tencent Advertising platform supports various ad formats, including native ads, rewarded video ads, splash ads, and interstitial ads. Advertisers can choose the appropriate ad format based on their needs and target audience, and utilize the Tencent Advertising platform for targeted placement and precision marketing.

Through the Tencent Advertising platform, advertisers can effectively interact with Tencent's user base and engage in brand promotion, achieving objectives such as brand exposure, user growth, and sales expansion. Tencent Advertising is committed to providing efficient, precise, and innovative advertising solutions to empower advertisers in the competitive market landscape.

We collected five consecutive days of logs from Tencent's advertising platform and extracted a large-scale industrial dataset with millions of samples. This dataset, named **Tenc-UnionAds**, encompasses over 300 features, including user features, ad features, and context features.

#### 2.1 Description

**Tenc-UnionAds** consists of three types of samples: click and conversion, click without conversion, and non-click. The quantity of samples for each category is presented in the following table. 

| CTR  | CVR  | Quantity |
| :--: | :--: | :------: |
|  1   |  1   |  212538  |
|  1   |  0   | 3691329  |
|  0   |  0   | 11181494 |

Additionally, **Tenc-UnionAds** provides over 300 features, including user features, ad features, and context features. These features are labeled with prefixes 1\_, 2\_, and 3\_, respectively. The number of features in each category is shown in the table below.

|   Feature   | Prefix | Count |
| :---------: | :----: | :---: |
|  **User**   |  1_*   |  285  |
|   **Ad**    |  2_*   |  41   |
| **Context** |  3_*   |   4   |



#### 2.2 Links（desensitized）

We have provided a lightweight example dataset under the "Dataset" directory for your convenience in quickly starting the training process. For the complete dataset, please refer to the link provided below.

> It is expected to be made public after May 17, 2024

### 3. Cite

Please cite our paper if you use our code or datasets in your publication.

