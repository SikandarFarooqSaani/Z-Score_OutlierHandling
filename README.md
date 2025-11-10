# Z-Score_OutlierHandling
# 📊 Handling Outliers Using Z-Score  
**AI Generated README**

---

## 📘 Overview
This experiment demonstrates how to **detect and handle outliers** using the **Z-Score method**.  
We use **CGPA** and **Resume Score** features from a dataset to observe the distribution, detect outliers, and handle them using capping and trimming.

---

## ⚙️ Steps and Process

### **1. Dataset and Visualization**
- Dataset is available in the repository.  
- Features used: **CGPA** and **Resume Score**.
- **Distribution plots** were created for both columns.  
  🖼️ *Image 1 attached.*

**Observations:**
- CGPA → *Not normally distributed*  
- Resume Score → *Normally distributed* ✅  
  Hence, Z-score can be applied on Resume Score.

---

### **2. Data Preparation**
- Performed **Train-Test Split** on the dataset.
- Imported:
  - **PowerTransformer** (method = *box-cox*)
  - **FunctionTransformer** (function = *square*)
- Applied transformations:
  - `FunctionTransformer` → applied on **CGPA**
  - `PowerTransformer` → applied on **Resume Score**
- Then, applied **StandardScaler** for scaling both features.

🖼️ *Image 2 attached — Distribution plots after transformation.*

---

### **3. Calculating Z-Scores**
- Printed **mean, standard deviation, min, and max** of CGPA.
- Calculated thresholds:
  - **Upper limit:** `mean + 3 × std`
  - **Lower limit:** `mean - 3 × std`
- Fetched all rows that crossed these boundaries → these are **outliers**.

---

### **4. Handling Outliers**
Two common approaches were applied:

| Method | Description | When to Use |
|--------|--------------|-------------|
| **Capping (Winsorization)** | Replace outliers with upper/lower limits | When data loss must be avoided |
| **Trimming (Removal)** | Remove rows with extreme values | When outliers are very few (less than 5%) |

> In this case, trimming was chosen as the dataset had very few outliers.

---

## 📎 Attachments
- **<img width="1320" height="448" alt="zscore 1" src="https://github.com/user-attachments/assets/f13ca713-ca5e-4541-a60f-53dcda977e54" />
** Initial distribution of CGPA & Resume Score.  
- **<img width="1328" height="448" alt="zscore2" src="https://github.com/user-attachments/assets/062d122d-5f4b-41d4-bc86-95d2583fa658" />
** Distribution after Power and Function transformation.

---

## 🧩 Key Insights
- Resume Score follows normal distribution → Z-Score suitable.
- CGPA required transformation to approximate normality.
- Outliers identified using ±3 standard deviations from the mean.
- Trimming slightly reduces data size but improves data quality.

---

> ⚠️ *This README is AI-generated and explains outlier handling using Z-Score, scaling, and transformations in a structured workflow.*

