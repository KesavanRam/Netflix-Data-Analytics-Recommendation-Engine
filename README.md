 
A comprehensive Data Analytics and Machine Learning project using the popular Kaggle Netflix dataset. This project explores Netflix's content strategy and library composition from 2008 to 2021, and implements a Content-Based Filtering Recommendation Engine using Natural Language Processing (NLP). 
 
## Project Overview 
- **Objective:** Clean messy streaming metadata, uncover production trends, and build an automated recommendation system based on plot descriptions. 
- **Tech Stack:** Python, Jupyter Notebook, Pandas, NumPy, Matplotlib, Seaborn, Scikit-Learn (TF-IDF, Cosine Similarity). 
- **Key Deliverable:** Cleaned final dataset (`netflix_cleaned_final.csv`) and a reusable recommendation pipeline. 
 
## Project Phases & Architecture 
 
### Phase 1: Data Cleaning & Preprocessing 
Raw data contained several structural gaps and unformatted columns. This phase ensured analytical readiness: 
- **Missing Value Imputation:** Addressed structural column gaps in `director` and `cast` by mapping missing markers to `'Unknown'`. Replaced missing `country` fields using the statistical mode. 
- **Feature Engineering:** Converted text-based timestamp strings into structured `datetime` formatting, successfully extracting new `year_added` and `month_added` dimensions. 
- **Index Optimization:** Handled cascading index gaps resulting from row drops by resetting the core DataFrame index (`reset_index`), protecting downstream vector loops. 
 
### Phase 2: Exploratory Data Analysis (EDA) 
Leveraged data visualizations to evaluate Netflix's operational landscape: 
- **Content Mix:** Generated proportional distribution models (Pie Charts) to evaluate the split between Movies (69.6%%) and TV Shows (30.4%%). 
- **Velocity Trends:** Mapped historical content-addition frequency (Seaborn Countplots) to uncover peak distribution years. 
- **Genre Saturation:** Flattened and exploded comma-separated categories to profile and rank the Top 10 dominating genres. 
 
### Phase 3: Text Vectorization & Recommendation Engine 
Built a Machine Learning recommendation pipeline to automate content mapping: 
- **NLP Processing:** Extracted content themes from raw `description` fields using `TfidfVectorizer` to remove stop words and vectorize plot matrices. 
- **Similarity Matrix:** Calculated geometric angles across text layers using `Cosine Similarity` to rate text similarity from 0 to 1. 
- **Automation Pipeline:** Constructed a modular Python function (`get_recommendations`) that queries similarity arrays to fetch top 5 contextual matches for target items like *Zombieland*. 
 
## How to Run the Project 
 
1. Clone the workspace repository: 
\`\`\`bash 
git clone https://github.com 
\`\`\` 
2. Install necessary dependencies: 
\`\`\`bash 
pip install pandas numpy matplotlib seaborn scikit-learn 
\`\`\` 
3. Boot up the Jupyter development environment: 
\`\`\`bash 
jupyter notebook 
\`\`\` 
4. Open the analysis file and run all cells sequentially. 
