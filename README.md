# NY Workers' Compensation Claims: Hearing Count Analysis 2000–2025

## Project Overview
This project analyzes over 1 million New York State workers' compensation claims filed between 2000 and 2025 to identify whether demographic, industry, or claim-specific characteristics are associated with higher hearing counts. Higher hearing counts indicate greater claim complexity, which translates directly to increased administrative and legal costs for the New York State Workers' Compensation Board.

The analysis was conducted in Python for data cleaning and exploratory data analysis, with findings visualized and presented in Tableau.

📊 **[View the Tableau Dashboard](https://public.tableau.com/app/profile/nathalie.gomez/viz/NYWorkersCompensationClaimsHearingCountAnalysis20002025/Presentation?publish=yes)**

---

## Research Question
> Do demographic, industry, or claim characteristics contribute to higher hearing counts in workers' compensation claims filed between 2000 and 2025?

---

## Tools & Technologies
- **Python** — data cleaning, exploratory data analysis (pandas, matplotlib, seaborn)
- **Jupyter Notebook** — analysis and documentation
- **Tableau** — interactive dashboard and presentation
- **Data Source** — [Assembled Workers' Compensation Claims: Beginning 2000](https://catalog.data.gov/dataset/assembled-workers-compensation-claims-beginning-2000), published by the New York State Workers' Compensation Board via data.ny.gov (last updated March 23, 2026)

---

## Dataset
- **Size:** 1M+ records
- **Time Range:** 2000–2025
- **Key Variables:** claimant demographics (age, gender, county), industry code and description, claim type, claim injury type, claim status, process stage, attorney representation, alternative dispute resolution (ADR), and hearing count
- **Derived Variables:** Age Group, Date Unknown flag, Age Unknown flag, Zip Unknown flag

---

## Key Findings

### Demographic Characteristics
- **Age** shows the strongest demographic association — hearing counts peak for claimants in their 40s (1.54) and decline for both younger and older workers
- **Gender** shows minimal variation — female (1.28) and male (1.25) claimants average nearly identical hearing counts
- **Location** shows a moderate pattern — urban counties and districts in the NYC metro area consistently average more hearings than upstate counterparts (Kings: 1.57 vs. Schuyler: 0.74)

### Industry Characteristics
- Industry is the strongest predictor identified among demographic and industry variables
- **Construction (23)** averages the highest hearing count at 2.28, while **Educational Services (61)** averages the lowest at 0.83 — nearly a 3x difference
- Missing industry classifications (code 0) average 1.14 hearings, confirming missing data does not skew the overall findings

### Claim Characteristics
- **Injury severity** is the strongest overall driver — Permanent Total Disability (PTD) claims average 11.06 hearings and PPD NSL claims average 8.95, while Cancelled, Non-Comp, and Med Only claims remain near zero
- **Process stage** compounds this further — Referee Reserved Decision claims average 39.00 hearings, suggesting how far a claim advances through the legal process is a key predictor of hearing activity
- **Attorney representation** adds an additional layer — represented claims average 3.26 hearings compared to just 0.21 for unrepresented claims, while ADR reduces hearing activity to near zero regardless of representation

---

## Recommendations
Targeting interventions at the highest burden categories — PTD, PPD NSL, Construction, Mining, and attorney-represented claims — could lower the overall average hearing count from **3.08 to 2.16** with a 30% reduction, representing a meaningful decrease in administrative costs across the Workers' Compensation Board's entire claims portfolio.

| Recommendation | Category | Projected Impact |
|---|---|---|
| Early intervention for severe injury claims | Claim Characteristics | High |
| Monitor attorney-represented claims | Claim Characteristics | High |
| Expand ADR adoption for high-risk industries | Industry | High |
| Target urban districts and counties | Demographics | Medium |

---

## Repository Structure
```
ny-wc-hearing-analysis/
│
├── README.md                  # Project overview and findings
│
├── data/
│   └── data_source.md         # Link to data.ny.gov source (dataset too large to upload)
│
├── notebooks/
│   ├── 01_wc_data_cleaning.ipynb # Data cleaning and derived variable creation
│   └── 02_wc_eda.ipynb           # Exploratory data analysis and Python visualizations
│
├── visuals/
│   ├── python_charts/         # Screenshots of Python EDA charts
│   └── tableau_screenshots/   # Screenshots of Tableau dashboard slides
│
└── requirements.txt           # Python dependencies
```

---

## How to Run
1. Clone this repository
2. Install dependencies: `pip install -r requirements.txt`
3. Download the dataset from [data.ny.gov](https://catalog.data.gov/dataset/assembled-workers-compensation-claims-beginning-2000) and place it in the `/data` folder
4. Run `01_data_cleaning.ipynb` first, then `02_eda.ipynb`

---

## Author
**Nathalie Gomez**  
[Tableau Public Profile](https://public.tableau.com/app/profile/nathalie.gomez)
