# BME 580 project - Building a Model to Study Stress Using Wearable Sensors
**Author**: Seijung Kim, Jiayue Liu, Achudh Balaraman
**GitHub repo**: seij001/BME580

## Database Information
Our open-source training dataset comes from a study conducted by researchers at the University of Louisiana at Lafayette. You can find this original dataset in the **"Stress_dataset"** folder. The data description of the dataset can be found here: https://datadryad.org/stash/dataset/doi:10.5061/dryad.5hqbzkh6f. This dataset also has an associated publication: https://www.nature.com/articles/s41597-022-01361-y  

Hosseini, S., Gottumukkala, R., Katragadda, S. et al. A multimodal sensor dataset for continuous stress detection of nurses in a hospital.Sci Data 9, 255 (2022). https://doi.org/10.1038/s41597-022-01361-y


## Files Included and Instructions to Run
Currently, the scripts for pre-processing, Exploratory Data Analysis, and statistical models are scattered in different scripts. We list those scripts and explain what kind of information you can find in each. We also list the data files you need to download to be able to run the scripts.
1. **Proposal graphs.Rmd** - RMD file where Achudh performed EDA on data. This Rmd file mainly includes distributions and density plots. - make sure to download **stress_all_sensorAchudh.csv** and **SurveyResults.xlsx**
* Proposal graphs.html - output file of Proposal graphs.rmd
* Allstress.png - Output from Proposal graphs.Rmd EDA stacked bar graph of all patient instances of every stress level
* Density7a.png - Output from Proposal graphs.Rmd EDA of patient 7a’s sensor dsitribution by stress level for all events
2. **bme580_project_EDA.Rmd** and **bme580_project_EDA_v2.Rmd** - RMD files where Seijung performed EDA. This Rmd file includes correlation matrices of different sensor modalities at different stress levels, a sample plot of sensor recordings (for EDA, HR, and skin temperature) and self-reported stress levels over the duration of a recording session, and a density plot of sensor data distributions.
* Please make sure to download **stress_all_sensor.csv**, **stress_all_sensor_7A_1587298286.csv**, **"data_train.csv"**, and  **"data_train_woMiss.csv"** along with the Rmd files.
3. **PCA_stress.Rmd** : Jiayue's script for PCA. performs PCA analysis on the stress dataset. You need **stress_all_sensor.csv** file to run this code. 
4. **Preprocessing.ipynb**: the code for combining all sensor data and survey results. Make sure you download the **Stress_dataset** (and unzip all the indivisual folders) and **SurveyResults.xlsx** to run this code. This code generates **data_train_woMiss** and **data_test_woMiss.csv** files. 
5. **LDA_stress.Rmd** : script for the LDA analysis, make sure you download the **data_train_woMiss.csv** and **data_test_woMiss.csv** to run this code. 
6. **bme580_decision_tree.Rmd**: script for generating our Random Forest model for classifying stress. Please also download the **data_train_woMiss.csv** and **data_test_woMiss.csv** to run this code. 
7. **bme580_boosted_tree.Rmd**: an "unfinalized" script for generating a boosted decision tree for classifying stress. This script cannot be run from RStudio and needs a DCC connection to manage the amount of computation needed to run the script.