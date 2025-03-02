# Cancer-Detection-Unsupervised-Learning

## Introduction
Michigan Medicine is committed to advancing cancer detection methods through the innovative use of patient health data. This analysis aims to explore the potential of unsupervised learning techniques—such as Principal Component Analysis (PCA), K-Nearest Neighbors (KNN), and clustering models—to enhance cancer diagnosis. The primary goal is to uncover patterns or anomalies in the data that align with cancer presence, **minimizing false negatives while maintaining high sensitivity and precision**. Success will be evaluated based on the sensitivity of the models in correctly identifying cancer cases and the interpretability of the findings for practical implementation in a clinical setting.

The outcomes of this analysis will guide Michigan Medicine in integrating data-driven insights into cancer diagnostics, enabling early detection and reducing mortality rates. By focusing on insights, this report provides actionable recommendations for incorporating unsupervised learning into medical decision-making processes.

## Methodology Overview
To achieve the objectives, we applied unsupervised learning methods to analyze the data. Key steps include:

Data Preprocessing: Cleaning and standardizing data.
Clustering Analysis: Using methods such as k-means and hierarchical clustering to identify patterns.
Outlier Detection: Applying advanced techniques to isolate potential high-risk cases.
Performance Metrics: Sensitivity and precision were prioritized, with a specific focus on minimizing false negatives.

<img width="828" alt="Screenshot 2025-01-22 at 20 31 39" src="https://github.com/user-attachments/assets/4a813546-d736-4f36-9f6f-707110c48c8c" />

### Interpretation of PCA
PC1 captures 37.78% of the variance, with each subsequent component contributing progressively less. Principal components are designed to maximize the variance captured, with each adding unique and meaningful information. Based on the pca result, to meet the goal of **capturing 97% of the total variance, the first 12 principal components are required**. Utilizing these components significantly reduces the dataset's dimensionality while retaining most of its critical information. This approach ensures the model effectively represents the underlying patterns in the data, enhancing its accuracy and interpretability.

![image](https://github.com/user-attachments/assets/b984f2ad-a075-4b7c-9839-8755062cdbbb)

#### Insight from KNN Outlier Dectection Visual
The dark blue points (Outlier = 0) represent data points that are considered within the "normal" range, meaning their KNN scores fall below the threshold set for outlier detection. The pink points (Outlier = 1) indicate the outliers, which are data points with KNN scores above the defined threshold (10%). However, the separation between outliers and normal points is not perfectly clear-cut. WE need to perform a confusion matrix analysis to evaluate the effectiveness of the outlier detection in identifying actual cancer cases.

#### Selecting Cancerous Clusters
<img width="347" alt="Screenshot 2025-01-22 at 20 33 35" src="https://github.com/user-attachments/assets/25fce1af-4cb5-42b5-8af7-9884fc2b63e0" />

Clusters 1 and 3 demonstrate distinct cancer-related characteristics based on their "Cancer_Proportion" values:

**Cluster 1**: With a cancer proportion of approximately 0.1379, this cluster likely contains a mix of cancerous and non-cancerous cases. While cancer-related data is present, it is not the dominant pattern, suggesting the cluster captures subtle overlaps or borderline cases.

**Cluster 3**: A cancer proportion of 1.0 indicates that this cluster exclusively consists of cancerous cases. This makes Cluster 3 a strong indicator of cancer-related data and highlights its potential utility in identifying clear-cut cancer diagnoses.

These insights suggest that while Cluster 3 is highly specific to cancer cases, Cluster 1 may represent patients with mixed or ambiguous health indicators, offering opportunities to refine detection in borderline cases.


<img width="333" alt="Screenshot 2025-01-22 at 20 34 12" src="https://github.com/user-attachments/assets/2f226f11-e46a-47cb-b599-3afd4aa3d603" />

#### Insights from K-Means Confusion Matrix
- Sensitivity (0.90476): The model is highly effective at identifying true positives (cancer cases). This aligns with the objective of minimizing false negatives, as missing cancer cases is critical.

- Specificity (0.78992): The model correctly identifies approximately 79.99% of non-cancer cases, though there is room for improvement to reduce false positives.

Overall, the model performs exceptionally well in sensitivity, aligning with the goal of minimizing missed cancer cases. However, its practical application would require addressing the high false positive rate to ensure efficient use of medical resources.

## Conclusion
In this analysis, unsupervised learning methods, specifically K-Means clustering and KNN-based outlier detection, were evaluated for their effectiveness in identifying cancer cases from patient health data. While these methods offer unique strengths, their limitations underscore the need for careful implementation and integration into clinical workflows. The focus throughout this analysis has been on **minimizing False Negatives**—ensuring that no cancer cases are missed—while also acknowledging the impact of False Positives, which can result in unnecessary testing and patient anxiety.

### Effectiveness of Methods:
- **K-Means Clustering:** The K-Means model demonstrated **strong sensitivity**, effectively identifying a high proportion of true cancer cases. This aligns well with the primary objective of minimizing false negatives, ensuring that as few cancer cases as possible are missed. However, the model suffered from low precision, indicating a tendency to overpredict cancer, which could lead to false alarms and unnecessary follow-up procedures.

- **KNN Outlier Detection:** KNN **successfully identified outliers** that correspond to cancer cases, but its performance was highly dependent on the choice of threshold. Sensitivity decreased as thresholds became stricter, and while precision improved, it came at the cost of missing more cancer cases. This trade-off requires careful consideration when applying this method in a practical healthcare setting.

**Overall, unsupervised learning methods like K-Means and KNN could serve as supplementary tools in cancer detection.** By flagging potential cancer cases, they could assist medical professionals in prioritizing patients for further evaluation. The ability to process unlabeled data is a key advantage, making these methods applicable even in scenarios where labeled datasets are limited or unavailable.

### Benefits and Risks of Unsupervised Learning:
The scalability of these models is a significant advantage. They can process large datasets efficiently, making them suitable for hospitals managing high patient volumes. Additionally, the high sensitivity of these models supports early detection, potentially improving patient outcomes by enabling timely interventions. Furthermore, these models can optimize resource allocation by prioritizing high-risk cases, reducing strain on diagnostic facilities and lowering overall healthcare costs.

Despite their potential, implementing these models in a clinical setting poses several challenges. The interpretability of these models also presents a challenge. Unsupervised methods are less transparent compared to traditional approaches, which could lead to skepticism among clinicians and patients. Ethical considerations, including the potential for model bias and accountability for errors, must also be addressed to ensure responsible implementation.

### Integrated Diagnosis Process
The proposed diagnosis process leverages unsupervised learning models, such as K-Means and KNN, as an initial screening layer. These models analyze patient data to identify anomalies or assign patients to high-risk clusters based on deviations from normal health metrics. Flagged cases are then prioritized for comprehensive diagnostic testing by healthcare professionals, ensuring that the models act as a complementary tool rather than a replacement for traditional methods. Continuous refinement of the models through feedback from confirmed diagnoses will enhance their sensitivity and precision over time, making them more aligned with clinical requirements.

## Final Thoughts
Unsupervised learning methods like K-Means and KNN show significant potential as supplementary tools for cancer detection, particularly in their ability to process large datasets and identify patterns. While False Positives may result in additional diagnostic follow-ups, this is less critical than minimizing False Negatives, which remains the primary focus to ensure no cancer cases are overlooked. These models should be integrated into a broader diagnostic system that includes human expertise for validation, addressing challenges such as interpretability and ethical concerns. With future improvements in precision, threshold optimization, and transparency, unsupervised learning can play a valuable role in improving efficiency, resource allocation, and patient outcomes in cancer detection workflows.
