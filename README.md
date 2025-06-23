# Sales-Forecasting-

Aim

This project explores the problem of store-level sales forecasting using historical weekly sales data. The goal was to investigate how different models — ranging from manual linear regression to ensemble tree methods — perform on structured, time-aware retail data. While the primary focus was on interpretability and hands-on understanding, additional models were tested for comparative insights.

Dataset :
The data spans 2010–2012 weekly sales for 45 stores, including:

    Store identifiers

    Weekly sales figures

    External features like temperature, fuel price, CPI, and unemployment

    Temporal features: year, month, holiday flags

Only data from 2010 and 2011 was used for training. The model was evaluated on its ability to predict 2012 sales, simulating a realistic forecasting scenario.

Models Explored

Random Forest Regressor :
To test performance on potentially nonlinear relationships and store-level quirks, a Random Forest Regressor was trained:

    Hyperparameters: n_estimators, max_depth, min_samples_split

    Achieved robust performance (~0.79–0.81 R²)
    Naturally handled categorical spillover and localized patterns
    Slightly less interpretable but less prone to overfitting than unregularized linear models

Linear Regression Using Sklearn :
A separate baseline linear regression model was built using sklearn to assess how well a standard closed-form solution performs on this structured dataset. This model was not used to validate the manual implementation, but rather to explore how a well-established method behaves under the same time-aware constraints.

    Delivered consistently strong performance on test data
    Benefited from proper scaling and a clean, interpretable feature set
    Demonstrated that simple models can perform exceptionally well in retail settings with seasonal and structured data

Manual Linear Regression (Gradient Descent) :
To build intuition and take full control over the training process, multivariate linear regression was implemented from scratch using NumPy and gradient descent. This allowed deeper insight into:

    Loss convergence

    Gradient behavior

    How feature scale and structure affect model dynamics

    Achieved high training performance with gradual, stable convergence
    Error dropped smoothly over iterations (visualized)


Neural Networks (Exploratory) :
A simple feedforward neural network was also tested, mainly to observe behavior rather than optimize for performance. It was not the focus of this project, and wasn’t heavily tuned.

    Useful for experimentation
    Not prioritized due to lack of interpretability and tuning overhead

 Tools & Stack

    Python: NumPy, pandas, matplotlib, scikit-learn

    No libraries used for manual regression — fully built using matrix operations

    Data splitting & evaluation done with future-aware logic (no leakage)

 Evaluation & Results

    All models were evaluated on unseen 2012 data

    Time-consistent train/test split to reflect real-world forecasting

    Sklearn Linear Regression performed strongest overall in terms of simplicity and accuracy

    Manual regression provided valuable intuition

    Random Forest proved reliable for capturing nonlinearities and cross-feature interactions

Summary

This project began as a hands-on learning exercise and evolved into a practical, performance-focused comparison between regression approaches. While not hyperparameter-heavy or optimized for leaderboard scores, it emphasizes:

    Clean pipeline design

    Understanding of model behavior

    Practical forecasting structure relevant to retail, FMCG, or supply chain domains
