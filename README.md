# Census Income Prediction Using ID3 Algorithm

This project predicts whether an individual's yearly income exceeds $50,000 based on various demographic attributes from the 1994 U.S. Census Bureau database. It involves building a decision tree using the ID3 algorithm for supervised learning, classifying income levels into two categories: "≤50K" and ">50K."

---

## **Dataset Description**
### **Features and Class Label**
1. **age**: The age of the individual (categorical: transformed from a continuous variable).
2. **workclass**: The type of employment (e.g., Private, Self-Employed, Government, etc.) (categorical).
3. **education**: The highest level of education attained (e.g., Bachelors, Masters, etc.) (categorical).
4. **education_num**: The number of years of education (categorical: transformed from a continuous variable).
5. **marital_status**: Marital status of the individual (e.g., Married, Single, Divorced) (categorical).
6. **occupation**: The individual's occupation (e.g., Tech, Healthcare, etc.) (categorical).
7. **relationship**: Relationship status (e.g., Husband, Wife, Not-in-family) (categorical).
8. **race**: Racial classification (e.g., White, Black, Asian) (categorical).
9. **sex**: Gender of the individual (categorical).
10. **hours_per_week**: The number of hours worked per week (categorical: transformed from a continuous variable).
11. **native_country**: Country of origin (e.g., United States, Canada, etc.) (categorical).
12. **high_income**: Indicates whether the individual's income is "≤50K" or ">50K" (class label).

---

## **Objective**
The goal of this project is to:
1. Build a decision tree using the ID3 algorithm to classify whether a person’s yearly income is "≤50K" or ">50K."
2. Optimize decision tree performance through entropy and information gain calculations.

---

## **Implementation Steps**

### **1. Data Preprocessing**
- **Datasets Used:**
  - Training Dataset: `census_training.csv`
  - Test Dataset: `census_training_test.csv`
- Verified that datasets are cleaned and structured with no missing or unknown data.

### **2. Helper Functions**
- **Entropy Calculation**: Measure uncertainty in the dataset.
- **Information Gain**: Determine the best feature for splitting.
- **Best Feature Selection**: Identify the attribute with the highest information gain.

### **3. Building the Decision Tree**
- Implemented the ID3 algorithm from scratch.
- Saved the tree as a dictionary of dictionaries for easier manipulation and visualization.

### **4. Validation**
- Tested the algorithm on smaller datasets (`playtennis.csv` and `emails.csv`) to ensure correctness.
- Verified that the decision tree structure matches expected outputs.

### **5. Training and Testing**
- Trained the model using `census_training.csv`.
- Evaluated accuracy using `census_training_test.csv`.
- Computed classification metrics and accuracy.

### **6. Tree Pruning**
- Implemented tree pruning to improve accuracy.
- Experimented with different thresholds for stopping tree growth.
- Observed classification accuracy improvements.

---

## **Setup Instructions**
### **Requirements**
- Python 3.x
- Libraries: `pandas`, `numpy`, `sklearn`, `graphviz`

### **Steps to Run**
1. Clone this repository:
   ```bash
   git clone https://github.com/NoellaButi/Census_Income_ID3.git
   cd Census_Income_ID3
   ```
2. Install required libraries:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the script for training and evaluation:
   ```bash
   python train_and_evaluate.py
   ```

---

## **Results**
### **Model Performance (Unpruned Tree)**
- **Accuracy:** 81.90%
- **Classification Report:**
  ```
              precision    recall  f1-score   support

           0       0.86      0.91      0.88     11330
           1       0.66      0.55      0.60      3698

    accuracy                           0.82     15028
   macro avg       0.76      0.73      0.74     15028
weighted avg       0.81      0.82      0.81     15028
  ```

### **Model Performance (Pruned Tree)**
- **Accuracy:** 82.35%
- **Classification Report:**
  ```
              precision    recall  f1-score   support

           0       0.86      0.91      0.89     11330
           1       0.67      0.55      0.60      3698

    accuracy                           0.82     15028
   macro avg       0.77      0.73      0.75     15028
weighted avg       0.81      0.82      0.82     15028
  ```

---

## **Visualization Files**
- **PlayTennis Decision Tree:** `Visualizations/playtennis_decision_tree.pdf`
- **Emails Decision Tree:** `Visualizations/emails_decision_tree.pdf`
- **Census Decision Tree (Unpruned):** `Visualizations/census_training_tree.pdf`
- **Census Decision Tree (Pruned):** `Visualizations/census_training_tree_pruned.pdf`

---

## **Acknowledgments**
- Dataset source: U.S. Census Bureau database.
- Inspired by ID3 algorithm implementations in machine learning research.
