# Machine-Learning-for-Wave-Forecast

In this work we implemented Machine Learning (ML) models to forecast the significant wave height (Hs) next to the Copacabana beach (Rio de Janeiro-Brasil) using as input the numerical data from a global wave model at an offshore point. The main goal is to predict events of high Hs in places not covered by computational models, contributing to emergency alerts in coastal regions. This approach was employed due to the lack of robust and continuous measured data in Brazil, making it a useful tool to be reproduced in locations with poor coverage of ocean measurements. 
Model training was performed using as input peak and swell wave data (direction, height, period) from WW3 global (https://pae-paha.pacioos.hawaii.edu /thredds/catalog.html) at 25° S and 43° W, and as output significant wave height (Hs) from a buoy located at 22.98° S and 43.17° W, available at SiMCosta (https://simcosta.furg.br). To make the time correlation between the input information and the Hs from the buoy we resolved the deep water wave velocity equation. For the training it was downloaded modelled and buoy data from 15-07-2016 (beginning of buoy record) to 01-06-2021. A considerable amount of these data was not used due to gaps in the buoy record, though.
We employed two ML models, extreme gradient boosting (XGBoost) and a two-layer Convolution Neural Network (CNN). The predicted results (solid lines) and the buoy data (dashed line) from 2021-06-01 to 2021-06-18 is shown in Figure 1. The Pearson correlation coefficients for XGBoost and CNN are 87.2 % and 81.6 %, respectively, and the Mean Absolute Error are 0.147 m and 0.176 m, respectively. It is important to observe that, despite the better results achieved with XGBoost, both models represented the events with high Hs well. Part of the difference between ML models and buoy data is related to the error in the WW3 modelled results. Besides, CNN is a very complex model, as different configurations of the layers may lead to better results than the obtained in the study. For the next steps we aim to fine-tune the parameters of XGBoost and CCN, and to train the model with more features, as atmospheric variables and wind waves parameters. 

<br />
<br />
<br />
<p align="center">
  <img src="https://github.com/fernandotcbarreto/stuff/blob/main/wave_for_ML.png">
</p>
