# Machine-Learning-for-Wave-Forecast

In this work we implemented Machine Learning (ML) models to forecast the significant wave height (Hs) next to the Copacabana beach (Rio de Janeiro-Brasil) using as input the numerical data from a global wave model at an offshore point. The main goal is to predict events of high Hs in places not covered by computational models, contributing to emergency alerts in coastal regions. 
<br />

Model training was performed using as input Peak and Swell wave data (direction, height, period) from WW3 global (https://pae-paha.pacioos.hawaii.edu /thredds/catalog.html) at 25° S and 43° W, and as output significant wave height (Hs) from a buoy located at 22.98° S and 43.17° W, available at SiMCosta (https://simcosta.furg.br). To make the time correlation between the input information and the Hs from the buoy we resolved the deep water wave velocity equation. For the training it was downloaded modelled and buoy data from 15-07-2016 (beginning of buoy record) to 01-06-2021. Part of these data was not used due to gaps in the buoy record, though.
<br />

We employed two ML models, extreme gradient boosting (XGBoost) and a two-layer Convolution Neural Network (shallow CNN). The predicted results (solid lines) and the buoy data (dashed line) from 2021-06-01 to 2021-06-18 are shown in Figure 1. The WW3 model result is also shown for comparison. The Pearson correlation coefficients for XGBoost, CNN, and WW3 are 91.1 %, 84.7 %, and 89.4 %, respectively, and the Mean Absolute Error are 0.123 m, 0.165 m, and 0.145, respectively. It is important to observe that, despite the better results achieved with XGBoost, both ML models represented well the events with high Hs. Part of the difference between ML models and buoy data is related to the error in the WW3 modelled results. Besides, CNN is a very complex model, as different configurations of the layers may lead to better results than the obtained in the study. For the next steps we aim to fine-tune the parameters of XGBoost and CCN, and to train the model with more features, as atmospheric variables and wind waves parameters.

<br />
<p align="center">
  <img src="https://github.com/fernandotcbarreto/stuff/blob/main/ml_fig_4comp.png">
</p>
Figure 1 - Predicted results (solid lines) from XGBoost, CNN, and WW3, and buoy data (dashed line) from 01-06-06-2021 to 18-06-2021. 
