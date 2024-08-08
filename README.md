Results of CONUS Nitrate LSTM model

Steps to install:
1. Clone the git in cmd terminal      >>git clone https://github.com/aayushpandit/EPA-CONUS-Nitrate-LSTM.git
2. Navigate to repository             >>cd EPA-CONUS-Nitrate-LSTM
3. Create environment                 >>conda env create -f environment.yml
4. Activate base repository           >>conda activate EPALSTM
5. Open jupyter notebook in browser   >>jupyter notebook
6. Run the code


github descriptions:

1. Arena = This superfolder contains data used in training custom hydroDL LSTM model from Chaopeng and his group.
  - Output = This folder is for 94 Nitrate model input which contains Gids.csv which is station IDs
      - const = area.csv contains upstream area at outlet of 94 nitrate stations.
      - crd = Coordinates in latitude and longitude of centroid of 94 nitrate station basins.
  - US = This folder contains shapefiles for US boundary and state boundary
  - Camels = This folder is for 754 streamflow model input which contains Gids.csv which is station IDs and Camels_attributes.csv is catchment attribute used for training model         
    - FromHPC =                        This folder contains results of training streamflow and nitrate model from HPC LSTM
      - 5Fold
        - conc_2 = This folder contains results of nitrate LSTM model. metrics.csv is model performance in each station, Observed and Simulated_compiled.csv are corresponding daily nitrate observations in USGS stations                          
        - flowmmday_3 = This folder contains results of flow LSTM model. metrics, observed and simulated data same as above.
    
2. Extra = This superfolder contains results of transfer learning in MRB
  - Forcing = This folder contains catchment attributes for 526 HUC8s in Mississippi river basin (MRB) east of 98th meridian
  - Shapefile = for HUC8s in Mississippi river basin east of 98th meridian
  - Predictions
      - Normalized
         - Conc_30 = This contains daily simulated nitrate concentration (mg-N/L) in 526 HUC8s in MRB
         - Flowmmday_20 = This contains daily simulated flow (mm/day) in 526 HUC8s in MRB
         - Load_30 = This contains nitrate yield (kg/km2/day) in 526 HUC8s in MRB, Yield obtained as Nitrate concentration * Streamflow
         - NDR_30 = This contains Nitrogen Delivery Ratio (NDR) defined as ratio of Load to surplus nitrogen from adaptation of Byrnes et. al., 2020.

3. environment.yml = This is file that contains list of all libraries used in python environment.
4. Code_for_Thesis = This contains jupyter notebook code to get plots of results shown in paper. 

References:
https://github.com/mhpi/hydroDL
Byrnes, D. K., Van Meter, K. J., & Basu, N. B. (2020). Long‐term shifts in US nitrogen sources and sinks revealed by the new TREND‐nitrogen data set (1930–2017). Global Biogeochemical Cycles, 34(9), e2020GB006626.
