Medical-Data-Visualizer

This project analyzes medical examination data to visualize the relationships between body measurements, blood test results, lifestyle choices, and cardiovascular disease using categorical plots and heatmaps.

📁 Dataset

File: medical_examination.csv  
Each row in the dataset represents a patient.  
Each column contains medical metrics or lifestyle indicators.

Features:

| Feature           | Description                                        |
|-------------------|----------------------------------------------------|
| age               | Age in days                                        |
| height            | Height in cm                                       |
| weight            | Weight in kg                                       |
| gender            | Gender (1 or 2)                                    |
| ap_hi             | Systolic blood pressure                            |
| ap_lo             | Diastolic blood pressure                           |
| cholesterol       | 1: normal, 2: above normal, 3: well above normal   |
| gluc              | 1: normal, 2: above normal, 3: well above normal   |
| smoke             | 0: No, 1: Yes                                      |
| alco              | Alcohol intake: 0: No, 1: Yes                      |
| active            | Physically active: 0: No, 1: Yes                   |
| cardio            | Target variable: 0: No disease, 1: Has disease     |


📊 Visualizations

1. Categorical Plot (catplot.png)
- Compares six features (cholesterol, gluc, smoke, alco, active`, overweight)
- Shows distribution of these features split by presence/absence of cardiovascular disease.
- Normalized:  
  - 0 = Good (healthy)  
  - 1 = Bad (unhealthy)

2. Heat Map (heatmap.png)
- Shows correlation matrix between all numeric features.
- Data is cleaned to remove:
  - Incorrect blood pressure readings (ap_lo > ap_hi)
  - Outliers in height and weight (values outside 2.5th–97.5th percentiles)

🧪 Instructions to Run

1. Make sure the following files are present:
   - medical_data_visualizer.py
   - medical_examination.csv
   - main.py (optional for testing)
   - test_module.py (for unit tests)

2. Install dependencies (if not already):
   bash
   pip install pandas matplotlib seaborn numpy

3. Run from a Python script or shell:

   python
   from medical_data_visualizer import draw_cat_plot, draw_heat_map

   draw_cat_plot()
   draw_heat_map()

4. Output plots:

   * ![catplot.png](
   * ![heatmap.png](https://github.com/rayyanm86/Medical-Data-Visualizer/blob/ef7e6e0db4f1f57ea208b4193380a81e856b9696/heatmap.png)

🛠️ Project Structure

├── medical_examination.csv         # Dataset
├── medical_data_visualizer.py     # Main analysis and visualization code
├── main.py                        # Optional file to test/run functions
├── test_module.py                 # Unit tests
├── catplot.png                    # Output: Categorical plot
└── heatmap.png                    # Output: Heatmap


✅ Features Implemented

* BMI-based overweight flag
* Normalization of glucose and cholesterol levels
* Melting, grouping, and plotting categorical features
* Cleaning medical data before correlation
* Heatmap with upper triangle masking


📌 Notes

* The BMI threshold used is **> 25** for overweight.
* All visualizations are generated using **Seaborn** and **Matplotlib**.
* Ensure your `medical_examination.csv` is formatted correctly with the exact column names.

📅 Author

This README was generated for the [Medical Data Visualizer](https://www.freecodecamp.org/learn/data-analysis-with-python/data-analysis-with-python-projects/medical-data-visualizer) project.
