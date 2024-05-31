# Targeted Antimicrobial Nanoparticles Design Using Machine Learning Reinforced Genetic Algorithm
## Abstract
Microbial infections caused by bacteria, viruses, fungi, and parasites pose significant healthcare challenges due to their ability to cause diverse diseases and adapt to antimicrobial agents. To address antimicrobial resistance, we propose a novel approach using a machine learning (ML) reinforced genetic algorithm (GA) to discover selective antimicrobial nanoparticles (NPs). The aim of this study is to develop an efficient ML reinforced GA to identify antimicrobial NPs that selectively target pathogenic microorganisms while minimizing harm to probiotic strains and host cells.
We began by compiling a comprehensive database to characterize nanoparticles and their antibacterial activity. Using this data, we trained CatBoost regression models to predict minimal concentration (MC) and zone of inhibition (ZOI), achieving 10-fold cross-validation (CV) R2 scores of 0.82 and 0.84, with root mean square errors (RMSE) of 0.46 and 2.41, respectively. Subsequently, we developed a ML reinforced GA to pinpoint the most effective selective antibacterial NPs. As a proof of concept, our approach identified a selectively antibacterial nanoparticle, CuO, which demonstrated targeted eradication of the pneumonia-causing pathogen K. pneumoniae with a significant minimal bactericidal concentration (MBC) difference of 392.85 µg/ml compared to Bacillus subtilis. These findings contribute to the emerging field of selective antimicrobial NPs and pave the way for future exploration of their synergistic interactions with drugs.
## Guidelines
At first, two repositories have been established: one for Minimal Concentration (MC) to identify selectively antimicrobial nanoparticles based on predicted minimal concentration, and another for Zone of Inhibition (ZOI) to identify nanoparticles based on predicted inhibition zone diameter. Each repository includes the genetic algorithm code, organized into separate folders for data, models, and genetic algorithm outputs. The data folder is subdivided into raw data, preprocessed data, and data visualization sections. The model folder contains scripts for model selection, optimization, validation, and performance visualization. The output folder houses results from the genetic algorithm, detailing the identification of selectively antimicrobial nanoparticles, and includes information on the optimization of parameters such as population size, generation number, and mutation and crossover rates.
## Data
Preprocessing steps were conducted as outlined in the V4_preprocessing_MIC.py file for MIC and V4_preprocessing_ZOI.py file for ZOI. Data distribution was visualized before and after preprocessing using pie charts, kernel density estimate (KDE) plots, and violin plots.
## Machine Learning
## Model Selection ## : We evaluated performance of various regression models on raw and preprocessed data for prediction of MC and ZOI using Python scripts in the LP folder. The results were stored in respective CSV files, and model performance was visualized using bar plots in the Visualization folder. CatBoost regressor and XGB regressor models emerged as the top performers and were subsequently selected for further optimization.
### Model Optimization ##: Hyperparameter tuning was performed to identify the best parameters for the CatBoost regressor and XGB regressor models. The CatBoost regressor exhibited slightly superior performance and was used for predicting MC and ZOI.
## Model Validation ## : Ten-fold cross-validation was conducted before assessing model performance on the test dataset. Additionally, the performance of the model on specific NPs was evaluated and visualized using scatter plots.
## Genetic Algorithm ##
To screen selectively antimicrobial NPs, a genetic algorithm was implemented, with all necessary files stored in the MIC and ZOI folders. Unique NP generation: Parameters for unique metal and metal oxide NPs were generated using the V4_ga_compd_generation.py file. The antimicrobial activity of these NPs was assessed against pneumonia-causing pathogenic bacteria on Staphylococcus aureus and Klebsiella pneumoniae, with predictions made using the optimized CatBoost regression model.
### NP mutation and crossover ##: The V4_crossing_mutation.py and V4_cross_modified.py files were used for the mutation, crossover, and evolution of nanoparticle parameters to enhance selective antimicrobial properties.
### Selective antimicrobial NP screening ###: The main file, V4_ga_main.py, orchestrated population generation and evolution up to a user-defined generation number. The fitness score of each individual NP was calculated by comparing the logarithm of MC or the difference in ZOI.
### Results: The top candidates of selectively toxic NPs generated by the algorithm were stored in the output folder for further analysis and consideration. ###
