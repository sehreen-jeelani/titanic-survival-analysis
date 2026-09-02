# Curious About the Titanic: My First Real-Data Project

An exploratory data analysis project where I wanted to understand what the Titanic passenger data could reveal about survival not just the overall rate, but the patterns behind it.

## Project Objective

Growing up, we all hear the story of the Titanic but when I started learning data analysis, I got curious about what the data could actually tell me. Was it really "women and children first," or did class, age, and family size matter more?

I wanted to see how survival connected to sex, passenger class, age, family size, title, cabin information, and port of embarkation both on their own and in combination.

This was my first time working with a messy, real-world dataset. My goal wasn't just to create charts, but to learn how to move from raw data to real observations and evidence.

## Workflow

1. **Data Wrangling** : Inspected the dataset, identified missing values and inconsistencies, and cleaned the data while considering how the gaps might affect the analysis.
2. **Feature Engineering** : Built new variables: `FamilySize`, `IsAlone`, `TitleGroup`, `Deck`, `CabinKnown`, `AgeGroup` to surface patterns the original columns didn't show directly.
3. **Survival Analysis** : Compared survival across sex, class, age, family size, title, cabin information, deck, and embarkation, including combinations of these factors.
4. **Data Visualization** : Built charts to make the main patterns easier to compare and interpret.

## Key Insights

**Sex showed the strongest survival difference:** 74.2% of female passengers survived vs. 18.9% of male passengers, and the gap remained strong across passenger classes and age groups.

**Class bought a better chance of survival:** rates dropped from 63.0% (1st class) to 47.3% (2nd class) to 24.2% (3rd class).

**Family size didn't follow a simple pattern:** solo travelers survived at about 30.4%, small family groups did better, and survival dropped again among the largest families.

**Age alone didn't tell a clean story** but combined with sex, the female-male gap held up strongly across most age groups.

**Title, cabin information, deck, and embarkation showed additional differences**, but these relationships overlap with other passenger characteristics and should not be interpreted as independent effects.

## Visualizations

Charts are stored in the [`visuals/survival_analysis/`](visuals/survival_analysis/) folder, including:

- Survival Rate by Sex
- Survival Rate by Passenger Class
- Survival Rate by Sex and Passenger Class
- Survival Rate by Age and Sex
- Survival Rate by Family Size
- Survival Rate by Title Group
- Survival Rate by Cabin Information
- Survival Rate by Deck
- Survival Rate by Port of Embarkation

## Technologies Used

- **Python 3**
- **Pandas** : data cleaning, transformation, and analysis
- **NumPy** : numerical operations
- **Matplotlib & Seaborn** : data visualization
- **Jupyter Notebook** : interactive analysis
- **Git & GitHub** : version control and project management

## How I Approached This Analysis

Since this was my first time working with a real dataset, I treated the project as both an analysis and a learning exercise.

I started by understanding the structure of the data and identifying missing values, then cleaned it, built new features, and moved gradually from single-variable comparisons to combinations of variables.

The biggest lesson: data analysis isn't just about getting an answer from a dataset. It's about deciding which questions are worth asking, checking whether the evidence actually supports the conclusion, and not confusing association with causation.

## Project Structure

```text
titanic-survival-analysis/
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
│   └── titanic_analysis.ipynb
├── visuals/
│   └── survival_analysis/
├── README.md
├── requirements.txt
└── .gitignore
```

## How to Run

1. Clone the repository:
```bash
   git clone https://github.com/sehreen-jeelani/titanic-survival-analysis.git
```
2. Install dependencies:
```bash
   pip install -r requirements.txt
```
3. Launch the notebook:
```bash
   jupyter notebook
```

## Limitations

- `Cabin` was missing for roughly 77% of passengers, so any cabin or deck based pattern is a lead worth exploring further, not a solid conclusion.
- This is an observational dataset the patterns found here show correlation, not proof of what caused survival.
- Sample sizes for some subgroups (very large families, rare titles) are small enough that those specific results should be read with caution.

## Conclusion

This was my first real dataset, and it taught me that analysis is really about learning to ask better questions not just writing code.

The answer to my original question turned out to be more complicated than a simple "women and children first." Sex showed the strongest single survival difference, while class was also strongly associated with survival. Family size, age, and title added further context when I looked at them alongside other variables.

More importantly, I learned that finding a pattern is only the beginning. I also have to ask how reliable that pattern is, what other variables might be connected to it, and what the data can't tell me.