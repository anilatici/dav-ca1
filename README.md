# Urban Livability Index (ULI)
 **A Composite Indicator for Measuring Urban Livability Across Cities**
## 📌 Project Overview
The **Urban Livability Index (ULI)** is a composite indicator that I designed to compare cities based on a few factors affecting quality of life. It combines different indicators such as economic, infrastructural, social and environmental into an index to help people assess urban livability.

## 📏 Key Dimensions 
ULI is built from 4 sub indices:
1. 🏡 **Economic Livability** (Housing, Cost of Living, Economy, Taxation)
2. 🚆 **Infrastructure & Connectivity** (Commute, Travel Networks, Internet Access)
3. 🏥 **Quality of Life** (Safety, Healthcare, Education, Environment, Leisure)
4. 👥 **Social & Inclusivity Factors** (Tolerance, Business Freedom, Recreation)

## 📂 Dataset
For this project, I am using **uaScoresDataFrame.csv** dataset, which contains urban data for 266 cities across the world. This dataset was gathered from: https://www.kaggle.com/datasets/orhankaramancode/city-quality-of-life-dataset?resource=download .

## ᯓ🏃🏻‍♀️‍➡️ How to Run the Analysis
```bash
# Clone the repository
git clone git@github.com:anilatici/dav-ca1.git

# Install required libraries
pip install pandas numpy matplotlib seaborn

# Run the analysis
python analysis.py
