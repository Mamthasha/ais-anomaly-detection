# ais-anomaly-detection

AIS-Anomaly-Detection
A machine learning framework for detecting and classifying abnormal behaviors in ship trajectories using AIS data.

About
This project implements and enhances the framework for ship abnormal behavior detection and classification (Rong et al., 2024). This repository provides a robust, end-to-end pipeline that transforms raw AIS trajectory data into actionable insights, utilizing machine learning to identify and categorize maritime traffic anomalies.

Technical Novelty & Enhancements :
While the baseline framework provides a solid foundation, this implementation introduces a refined processing pipeline to address data noise and classification ambiguity:

Optimized Behavioral Segmentation (K-Means): Replaced static thresholding with an automated K-Means clustering approach. By leveraging Elbow and Silhouette score analysis, the model achieves precise identification of 4 distinct behavioral clusters, ensuring higher consistency in segmenting ship motion.

Robust Noise Mitigation (Mahalanobis Distance): To tackle real-world AIS data volatility, we integrated a statistical filtering layer using Mahalanobis Distance. This effectively isolates outliers as a distinct "Class 5," preventing noise from biasing the Random Forest classifier and significantly improving predictive reliability.

Enhanced Data Integrity: Implemented a rigorous preprocessing stage including feature normalization and balanced sampling (undersampling of the majority class) to ensure the model generalizes well across diverse maritime traffic scenarios.

Pipeline Architecture
Data Preprocessing: Quality filtering and Min-Max feature normalization.

Behavioral Clustering: K-Means clustering to define the behavior classes.

Outlier Mitigation: Mahalanobis distance analysis to isolate noisy AIS samples.

Classification: Random Forest model trained on the refined, balanced dataset.

Project Structure
Plaintext
├── 01_AIS_Data_Exploration.ipynb
├── 02_Data_Preprocessing_and_Clustering.ipynb
├── 03_Abnormal_Behavior_Detection.ipynb
└── 04_Behavior_Classification_Training.ipynb
Results
By implementing these enhancements, the framework achieves an accuracy of 70.97%, demonstrating increased stability in classifying complex maritime traffic patterns compared to baseline models.

References
Rong, H., Teixeira, A.P., & Guedes Soares, C. (2024). "A framework for ship abnormal behaviour detection and classification using AIS data." Reliability Engineering and System Safety.


Developed as part of a research-oriented machine learning project.
