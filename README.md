## Key Findings

### Adult Income (Classification)
- **SVM** achieved the highest mean CV accuracy (0.8526) with statistically significant improvement over Logistic Regression.  
- **Random Forest** and **Logistic Regression** both reached ~0.90 AUC, showing strong separability.  
- **Decision Tree** underperformed in recall despite high precision.  
- Robustness analysis showed:
  - All models heavily relied on **capital-gain**, **marital-status**, and **education-num**.  
  - Ablation of top features dropped Random Forest’s accuracy by ~2.6 percentage points, making it most sensitive.  
  - Noise injection (σ = 0.1–0.3) had negligible impact, confirming resilience.  
  - Training-size sensitivity: models remained stable even at 25% training data.  
- **Efficiency trade-off**: SVM took ~93s to train, while Logistic Regression and Random Forest trained in <1s.

### Forest Cover Type (Classification)
- **Random Forest** achieved the best mean CV accuracy (0.768) and AUC (0.942), significantly outperforming Logistic Regression.  
- **Decision Tree** provided competitive accuracy (0.727 CV) at minimal computational cost.  
- **SVM with RBF** was excluded due to prohibitive runtime (dataset: 581k samples, 54 features).  
- Key predictors: **Elevation** and **Horizontal Distance** features dominated across models.  
- Ablation tests confirmed ensembles were most affected by removing top predictors.  
- All models showed stability with noise injection and varying training sizes.  
- **Efficiency**: Logistic Regression (0.65s), Decision Tree (0.11s), Random Forest (1.02s). Trade-off justified by Random Forest’s accuracy gains.

### California Housing (Regression)
- **Random Forest** was the top performer with mean R² = 0.791 (test R² = 0.773), a **34% improvement** over linear models.  
- **SVR** followed at R² = 0.728 but required **700× longer training** than Linear Regression.  
- **Linear and Ridge Regression** overlapped at R² = 0.576, showing limited benefit from regularization.  
- Feature importance:
  - **Median Income** was the strongest predictor.  
  - Geographic features (Latitude, Longitude) captured clear spatial patterns (north-south price gradient).  
- Robustness analysis:
  - Linear models were most stable under noise but had lower baseline accuracy.  
  - Random Forest lost ~5.7 pp in R² when top features were removed but still outperformed others.  
  - SVR showed instability with small training sizes (even negative R²).  
- Efficiency: Linear models (~0.03s), Random Forest (~3.3s), SVR (~21.4s).  

---

## Report
The full project write-up with methodology, robustness tests, and advanced analysis is available here:  
[ ML_Final_Project.pdf](/ML_Final_Project.pdf)

---

### Authors
- Venkata Krishna Rayalu Garapati  
- Ayush Vineet Jain  
- Varun Agarwal  
Khoury College of Computer Sciences, Northeastern University
