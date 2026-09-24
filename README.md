# 🚢 Titanic Survival Analysis: EDA & Feature Engineering

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-ffffff?style=flat-square&logo=python&logoColor=black)
![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=flat-square&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

An exploratory data analysis project looking into the passenger patterns behind survival on the RMS Titanic. Instead of jumping straight into machine learning, I focused on data cleaning, engineering new features, and seeing what the numbers actually reveal.


## 📌 Why I Built This

We've all heard the story of the Titanic, but when I started learning data analysis, I wanted to see what the data actually says. Was it strictly "women and children first," or did passenger class, age, and family dynamics play a bigger role than people think?

I set out to explore how survival connected to sex, class, age, family size, deck levels, and embarkation ports—both individually and combined.

This was my first time working with a messy dataset. My goal wasn't just to generate pretty charts, but to learn how to ask better questions, clean missing data without making bad assumptions, and distinguish between a genuine pattern and pure coincidence.


## 🛠️ Key Technical Features & Workflow

1. **Data Cleaning & Missing Value Strategy:** Analyzed missing data patterns in `Age`, `Cabin`, and `Embarked`. Used median imputation for missing age values and handled missing embarkation and cabin entries without distorting distributions.
2. **Custom Feature Engineering:**
   - **`FamilySize` & `IsAlone`:** Combined `SibSp` and `Parch` to quantify family dynamics and distinguish solo travelers from groups.
   - **`TitleGroup`:** Extracted honorifics from `Name` strings (e.g., *Mr, Mrs, Miss, Master, Officer*) to retain social status signals.
   - **`Deck` & `CabinKnown`:** Derived cabin decks from raw strings while creating a flag to track whether cabin location data was available.
   - **`AgeGroup`:** Binned continuous ages into logical life stages (*Child, Teen, Adult, Senior*) for clearer categorical comparisons.
3. **Exploratory Bivariate & Multivariate Analysis:** Examined single variables first, then combined them to observe how overlapping factors were associated with survival outcomes.
4. **Data Visualizations:** Built comparative charts using Seaborn and Matplotlib to visualize the main survival patterns.


## 📊 Key Findings & Visuals

### 1. Survival Rate by Sex
- **What the data showed:** Sex was by far the clearest differentiator in survival rate among the demographic variables I checked. **74.2%** of female passengers survived compared to **18.9%** of male passengers.

![Survival Rate by Sex](visuals/survival_analysis/survival_by_sex.png)


### 2. Survival Rate by Passenger Class
- **What the data showed:** Passenger class showed a clear difference in survival rates. First class passengers achieved a **63.0%** survival rate, compared to **47.3%** in second class and **24.2%** in third class.

![Survival Rate by Passenger Class](visuals/survival_analysis/survival_by_pclass.png)


### 3. Combining Sex and Passenger Class
- **What the data showed:** The survival advantage for women held across every class, though third class female passengers (**50.0%**) fared noticeably worse than those in first class (**96.8%**).

![Survival Rate by Sex and Passenger Class](visuals/survival_analysis/survival_by_sex_pclass.png)


### 4. Survival Rate by Age and Sex
- **What the data showed:** Children under 12 showed higher survival rates across the groups analyzed. While this aligns with historical accounts of prioritizing children during evacuation, the dataset alone cannot establish whether that was the cause of the difference.

![Survival Rate by Age and Sex](visuals/survival_analysis/survival_by_age_sex.png)


## 📁 Repository Structure

```text
titanic-survival-analysis/
├── data/
│   ├── raw/                   # Original dataset files
│   └── processed/             # Cleaned data with engineered features
├── notebooks/
│   └── titanic_analysis.ipynb # Step-by-step analysis notebook
├── visuals/
│   └── survival_analysis/     # Exported plots and charts
├── .gitignore                 # Files excluded from Git
├── README.md                  # Project documentation
└── requirements.txt           # Python dependencies
