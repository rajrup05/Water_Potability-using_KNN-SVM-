## Water Potability Prediction – Machine Learning

This project builds and compares machine-learning models to classify whether water is potable using physicochemical attributes. The workflow includes preprocessing, scaling, model training, and evaluation across multiple algorithms.

## Dataset

The **Water Potability** dataset provides measurements such as:

* pH
* Hardness
* Solids
* Chloramines
* Sulfate
* Conductivity
* Organic Carbon
* Trihalomethanes
* Turbidity
* Potability (target)

Missing values are handled using median imputation to retain useful distributional characteristics.

## Project Structure

* **Data Loading:** Imports the dataset into a pandas DataFrame.
* **Feature/Target Split:** Separates independent variables and the potability label.
* **Preprocessing:**

  * Median imputation
  * Min-Max scaling
* **Train/Test Split:** Stratified 80/20 split to maintain class balance.

## Models Implemented

### 1. K-Nearest Neighbors (KNN)

* Tests ( k = 1 \ldots 29 ).
* Logs accuracy for each value of ( k ).
* Identifies the best-performing neighborhood size.

### 2. Support Vector Machine (SVM)

* Evaluated with linear, polynomial, and RBF kernels.
* Produces metrics including accuracy, confusion matrix, precision, recall, and F1-score.
* Includes a dedicated RBF SVM run for detailed classification performance.

## Results Overview

* KNN accuracy depends heavily on the chosen value of ( k ).
* SVM models exhibit stronger and more stable performance.
* RBF SVM typically achieves the best balance across evaluation metrics.

## How to Run

### Local Environment

1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Place `water_potability.csv` inside a `data/` directory.
4. Launch the notebook:

   ```bash
   jupyter notebook notebook.ipynb
   ```

### Google Colab

1. Upload the notebook (`.ipynb`) to Google Colab.
2. Upload `water_potability.csv` manually using the Colab file browser
   **or** mount Google Drive and place the dataset there:

   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```
3. Adjust dataset paths if necessary (e.g., `/content/data/...` or drive paths).
4. Run all cells in sequence.

## Features

* Fully reproducible ML pipeline
* Multi-model comparison
* Hyperparameter experimentation
* Clear evaluation metrics for model selection.
