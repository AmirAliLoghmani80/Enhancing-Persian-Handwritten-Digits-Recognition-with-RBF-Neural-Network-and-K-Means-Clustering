# Enhancing Persian Handwritten Digits Recognition with RBF Neural Network and K-Means Clustering

This project was done as an exercise in **Learning in Brain and Machine 1 course**. It focuses on improving the recognition accuracy of Persian handwritten digits by combining a **Radial Basis Function (RBF) Neural Network** with **K-Means clustering** for optimized center selection. The integration of K-Means with RBF aims to enhance the initialization process and improve the overall performance of the recognition system.

## Project Overview

### Key Objectives:
1. **Feature Extraction**: Use zoning methods to extract features from Persian handwritten digits.
2. **Center Selection**: Utilize K-Means clustering to select neuron centers for the RBF neural network, improving center initialization.
3. **Weight Updating**: Train the RBF neural network to classify handwritten digits based on the extracted features.
4. **Comparison**: Evaluate the performance of the proposed method against traditional classification techniques, including k-Nearest Neighbor (k-NN) and Parzen Window.

## Methods

### 1. Preprocessing
Before training, all images of Persian handwritten digits were resized to a uniform dimension to ensure consistency. Unlike typical resizing, the images were centered within zero matrices to preserve the height-width ratio, which is crucial for maintaining classification accuracy.

### 2. Feature Extraction: Zoning
A **Zoning Feature Extraction** technique was used, where each image was divided into a 5x5 grid. The average pixel value in each zone was calculated, resulting in a feature vector of 25 elements for each image.

### 3. RBF Neural Network with K-Means
- **K-Means for Center Selection**: The K-Means algorithm was employed to select the initial neuron centers in the RBF neural network. By clustering the input data, the algorithm identified representative centers, providing a more effective initialization for the RBF neurons.
- **Weight Updating**: After the neuron centers were established through K-Means, the weights of the RBF neural network were updated based on the calculated radial basis functions (RBFs) between the input data and the selected centers.

### 4. Evaluation
The **Silhouette Score** was used to determine the optimal number of clusters for K-Means. Based on the analysis, the optimal number of clusters was found to be 256, which was used for center selection in the RBF network.

## Results

| Classification Model | Accuracy (%) |
|----------------------|--------------|
| **Nearest Neighbor**  | 86.9%        |
| **k-NN**              | 89.3%        |
| **Bayes**             | 83.0%        |
| **Parzen Window**     | 85.4%        |
| **K-Means (without RBF)** | 84.6%    |
| **RBF + K-Means**     | 78.0%        |
| **Average Accuracy**  | 84.5%        |

### Conclusion:
- The **k-NN** classifier achieved the highest accuracy (89.3%) on the dataset, outperforming the other models.
- The **RBF + K-Means** approach, while innovative, did not surpass the traditional methods in this experiment. There is potential for improving the implementation, especially since built-in functions were not used in the RBF network.
- Further improvements to the RBF network and adjustments to the K-Means clustering process may enhance performance in future iterations.
