<h1 style="text-align: center;">Med AI</h1>

MedAI is an intelligent chatbot developed by a collaborative team aimed at providing insightful medical information and assistance to users. Leveraging state-of-the-art machine learning techniques, including natural language processing (NLP) and multimodal capabilities, MedAI can understand and respond to a wide range of medical queries efficiently


# **Title**
<a id="idtop"></a>  
<img src="./resources/content/gs1.jpg" width="750">

## Table of Contents
* [Project Overview](#overview)
* [Business Scenario](#business-scenario)
* [Data PreProcessing](#data-preprocessing)
* [Model Training and Testing](#model-training-and-testing)
* [Visuals and Explanations](#visuals-and-explanations)
* [Demos and Slideshow](#demos-and-slideshow)
* [Final Summary](#final-summary)
* [Recommendations and Conclusion](#recommendations-and-conclusion)
* [Project Contributors](#project-contributors) 
* [Project Structure](#project-structure)
* [Repository Links](#repository-links)
* [References](#references)

## Project Overview 
Text



[🔼 Back to top](#idtop)
<hr>

## Business Scenario
Text

[🔼 Back to top](#idtop)
<hr>

## Data PreProcessing
* Sub Title
  * Text
* Sub Title
  * Text
  * Text
* Sub Title
  * Text
[🔼 Back to top](#idtop)
<hr>

## Model Training and Testing  
* Sub Title
  * Text
* Sub Title
  *Text
  * Text
* Sub Title
  * Text [🔼 Back to top](#idtop)
<hr>

## Visuals and Explanations
* Text

**Title**
![image)Link.png
*Text

**Title**
![image]Link.png)
*Text

**Title**
![image]Link.png)
*Text

**Title**
![image]Link.PNG)
*Text
![image]Link.PNG)
*Text

**Title**
![image]Link.png)
*Text
![image]Link.png)
*Text

**Interest Rate Prediction Analysis**
![image](resources/content/dex_lr1.png)
linear Regression 1.
![image](resources/content/dex_lr2.png)
linear Regression 2.

[🔼 Back to top](#idtop)
<hr>

## Demos and Slideshow
* Title
  * Navigate to [Demo]path demo.gif)    
* Text
  * Navigate to [Demo](resources/content/rb_demo.gif)
* AMES Feature Analysis
  * Navigate to [Demo](resources/content/wat_demo.gif)
* Interest Rate Prediction Analysis
  * Navigate to [Demo](resources/content/dex_demo.gif)  
* Project #2 - Team #6 - StreamLit Demonstration 
  * Navigate to [StreamLit Demo Files](resources/website)
* Project #2 - Team #6 - Powerpoint Presentation 
  * Navigate to [Slideshow PPT](resources/presentation/Golden-State-Housing-Insights.pptx)
  * Navigate to [Slideshow PDF](resources/presentation/Golden-State-Housing-Insights.pdf)

[🔼 Back to top](#idtop)
<hr>

## Final Summary
  * Housing Price Prediction using Zillow Data Analysis
    * To identify the five most optimal metro areas for investment in California, we automated the process of running time series models (ARIMA and SARIMA) for each of the 34 metro areas. This automation was necessary due to the impracticality of manually analyzing each area. We evaluated the models' accuracy by comparing their predictions for December 2024 with actual observed values. For initial optimization run, the ARIMA model's predictions were 9.12% off with 91% accuracy, while the SARIMA model's predictions were 14% off with 86% accuracy. For the final optimization run, the ARIMA model's predictions were 7.94% off with 93% accuracy.
    * Despite SARIMA showing better ROI for the top 5 metro areas, ARIMA's lower error rate suggests it could be more accurate with additional data. The ARIMA model predicted a return on investment (ROI) percentage range of 4% to 6%, whereas the SARIMA model predicted an ROI range of 5% to 6%. For model optimization, both ARIMA and SARIMA had high RMSE values, 2432.90 and 3547.65 respectively. High RMSE indicates a flawed predictive model. For the final optimization run the ARIMA model predicted a return on investment (ROI) percentage range of 4% to 8%. For model optimization, we lowered RMSE to 1424.48. 
  * Housing Feature Analysis  
    * The analysis revealed that the five most influential factors in predicting house prices are Median Income (MedInc), House Age (HouseAge), and Average Number of Rooms (AveRooms), Latitude, and Average Occupancity(AveOccup). Among these, Median Income exhibits the strongest correlation with housing prices, suggesting that areas with higher median incomes tend to have more expensive homes. The model, trained using linear regression, achieved an R-squared (R²) score of approximately 63%. Even after refinment using hypertuning and comparing the Random Forest Model the maximum accuracy score topped at 70.47%. These findings highlight that there is an impact of economic factors on housing prices though not wholly reliable. Access to more impactful features will be needed. Additonally, exterior quality is a very important feature, followed by Garage size and most of the living space size features. Kitchen quality is right behind exterior quality and the overall size of the house. 
  * Interest Rate Prediction Analysis
    * The models are designed to forecast future interest rates based on historical trends. Assuming these patterns persist, the models can potentially predict whether interest rates will rise, fall, or remain stable in the near term (e.g., the next few months). The plot titled "Interest Rate Prediction until Feb 2025" illustrates an upward trend in interest rates over recent years. Consequently, we would generally expect a slowdown in the housing market, characterized by potentially decreased sales and slower home price appreciation.
    * The model forecasts an increase in interest rates into February 2025. This is primarily because interest rates directly influence mortgage rates. Higher mortgage rates make homes less affordable, leading to decreased demand and potentially lower home prices. Conversely, lower mortgage rates make homes more affordable, potentially increasing demand and driving up home prices.
    [🔼 Back to top](#idtop)
    <hr>

## Recommendations and Conclusion
  * Client Recommendation
    * Top 5 California Metro Areas with the highest ROI and best potential for a solid investment
      * Merced, CA - ROI @ 1 year - 6%
      * Modesto, CA - ROI @ 1 year - 5%
      * Sacramento, CA - ROI @ 1 year - 4% 
      * Bakersfield, CA - ROI @ 1 year - 4%
      * Oxnard, CA - ROI @ 1 year - 3%
    * Features to consider-
        * House age
        * Exterior Quality
        * Garage Size
        * Living space size
        * Kitchen quality
    * Interest Rate Prediction
      * Increase in interest rates into Q1 2025
  * Conclusion
    * The prediction percentages come from models trained on five years of data to predict two years ahead. We plan to use ten years of training data to predict just one year ahead. This suggests that our future predictions will likely be even more accurate than those in this validation test. By leveraging a larger dataset, we aim to enhance the reliability and precision of our investment recommendations.

[🔼 Back to top](#idtop)
<hr>

## Project Contributors
- Chris Gilbert <br>   
- Dexter Johnson <br>   
- Jacinto Quiroz <br>   
- Joel Freeman <br>  
- Sean Burroughs <br>    
- Will Atwater <br>    

[🔼 Back to top](#idtop)
<hr>

## Project Structure
```
├─ code
├── cg_eda_arima.ipynb
├── dex_pred_analysis.ipynb
├── rb_pred_features.ipynb
├── watwater_final.ipynb
├─ resources
├── data
├─── fed-rates.csv
├─── metro_zillow.csv
├─── AmesHousing.csv
├── content
├─── cd_mtop.png
├─── cg_demo.gif
├─── cg_predictions.png
├─── cg_roi.png
├─── dex_demo.gif
├─── dex_lr1.png
├─── dex_lr2.png
├─── gs1.jpg
├─── rb_demo.gif
├─── rb_heat.png
├─── rb_linearreg.png
├─── wat_ames_feat.png
├─── wat_ames_featimp.png
├─── wat_demo.gif
├─ README.md
```
[🔼 Back to top](#idtop)
<hr>

## Repository Links
* Code: Code - Directory containing all of the the code
  * Housing Price Prediction using Zillow Data Analysis
    * Navigate to [Link to Housing Price Prediction using Zillow Data Analysis](code/cg_eda_arima.ipynb)    
  * Housing Feature Analysis 
    * Navigate to [Link to Housing Feature Analysis](code/rb_pred_features.ipynb)
    * Navigate to [Link to Housing trim Analysis](code/will_pred_features.ipynb)
  * Interest Rate Prediction Analysis
    * Navigate to [Link to Interest Rate Prediction Analysis](code/dex_pred_analysis.ipynb)  
* Content: 
  * Navigate to [resources/content](resources/content) - Directory containing all images of plots created in Jupyter Notebook and demos.
* Data: 
  * Navigate to [resources/data](resources/data) - Directory containing all of the csv files used by the code

[🔼 Back to top](#idtop)
<hr>

## References
* https://www.zillow.com/research/data/
* https://www.kaggle.com/datasets/shashanknecrothapa/ames-housing-dataset
* https://scikit-learn.org/stable/modules/generated/sklearn.datasets.fetch_california_housing.html

[🔼 Back to top](#idtop)
<hr>
