# Diabetes Prediction (Generative Models)

This project explores **generative models** for predicting diabetes from patient data.  

## Generative vs Discriminative Models
- **Generative models** learn the *joint probability distribution* `P(X, y)`.  
  - They try to model how the data is generated for each class.  
  - Example: Naive Bayes, LDA, QDA.  
- **Discriminative models** learn the *decision boundary* directly via `P(y|X)`.  
  - They focus only on separating classes, not modeling how the data was created.  
  - Example: Logistic Regression, SVM, Neural Networks.  

In this notebook, we focus on **generative algorithms**.

---

## Models Implemented
### 1. Gaussian Naive Bayes (GNB)
- Assumes features are conditionally independent given the class.  
- Simple, fast, but often unrealistic since features may be correlated.  
- **Result:** High accuracy but very poor recall (misses most positive cases).  

### 2. Linear Discriminant Analysis (LDA)
- Assumes each class follows a Gaussian distribution with **shared covariance matrix**.  
- Finds a linear boundary that best separates the classes.  
- **Result:** Best performance overall, with balanced accuracy, precision, and recall.  

### 3. Quadratic Discriminant Analysis (QDA)
- Similar to LDA, but allows **class-specific covariance matrices**.  
- More flexible, but prone to overfitting.  
- **Result:** Accuracy okay, but failed to detect positive cases.  

---

## Dataset
- **Samples:** 100,000 patients  
- **Features:**  
  - Demographic: `gender`, `age`  
  - Clinical: `hypertension`, `heart_disease`, `bmi`, `HbA1c_level`, `blood_glucose_level`  
  - Lifestyle: `smoking_history`  
- **Target:** `diabetes` (0 = No, 1 = Yes)

---

## Results
| Model                | Accuracy | Precision | Recall |
|-----------------------|----------|-----------|--------|
| Gaussian Naive Bayes  | ~91.5%   | 1.00      | 0.01   |
| Linear Discriminant Analysis (LDA) | ~95.6%   | 0.86      | 0.58   |
| Quadratic Discriminant Analysis (QDA) | ~91.4%   | 0.00      | 0.00   |
