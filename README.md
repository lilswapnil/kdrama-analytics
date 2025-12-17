# K-Drama Dataset Analysis & Preprocessing

A machine learning project for cleaning, preprocessing, and analyzing the Ultimate Korean Drama Dataset (1969–2025).

## 📊 Dataset

**Source:** [The Ultimate Korean Drama Dataset](https://www.kaggle.com/datasets/zeynepesennur/the-ultimate-korean-drama-dataset-19692025?resource=download)

**Size:** 1,000+ K-dramas with metadata spanning 1969–2025

**Key Features:**
- `title` – Drama title
- `rating` – IMDB rating (0–10)
- `votes` – Number of votes
- `genres` – Genre(s)
- `synopsis` – Plot summary
- `runtimeMinutes` – Episode duration
- `startYear` / `endYear` – Broadcast years

## 🎯 Project Goals

1. **Data Cleaning** – Handle missing values, outliers, and inconsistencies
2. **Preprocessing** – Scale, normalize, and encode categorical variables
3. **Analysis** – Identify trends, top dramas, genre distribution, ratings patterns
4. **Visualization** – Generate insights with plots and heatmaps

## 🛠️ Installation

### Prerequisites
- Python 3.8+
- pip or conda

### Setup

1. **Clone the repo:**
   ```bash
   git clone <your-repo-url>
   cd learn_ml_ai
   ```

2. **Create & activate virtual environment:**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate  # macOS/Linux
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

## 📁 Project Structure

```
learn_ml_ai/
├── data/
│   ├── kdramas.csv                      # Raw dataset
│   └── cleaned_preprocessed_data.csv    # Cleaned output
├── test.ipynb                           # Main analysis notebook
├── requirements.txt                     # Dependencies
└── README.md                            # This file
```

## 📝 Workflow

### 1. **Data Import & Exploration**
- Load dataset from CSV
- Check data types and shape
- Visualize missing data patterns

### 2. **Data Cleaning**
- Drop rows missing critical columns (`genres`, `votes`, `synopsis`)
- Fill numeric columns with mean values
- Fill categorical columns with mode or "Unknown"

### 3. **Outlier Detection**
- Compute z-scores for numeric features
- Remove rows with z-score > 3
- Cap extreme values (e.g., votes at 95th percentile)

### 4. **Scaling & Normalization**
- **Min-Max Scaling** (0–1 range)
- **Z-score Standardization** (mean=0, std=1)

### 5. **Encoding**
- One-hot encode categorical variables (`genres`)
- Preserve non-numeric columns

### 6. **Analysis & Visualization**
- Top 50 K-dramas by rating
- Top 20 K-dramas by votes
- Genre distribution (bar chart)
- Rating distribution (histogram)
- Rating vs. votes (scatter plot, log-scaled)
- Releases per year (line chart)
- Correlation heatmap (numeric features)
- Runtime distribution (box plot)

## 🚀 Usage

### Run the Full Pipeline

Open `test.ipynb` in Jupyter/VS Code and run all cells:
```bash
jupyter notebook test.ipynb
```

Or in VS Code: Click **Run All** (⏭️) in the notebook editor.

### Generate Results

The cleaned data is saved to:
```
data/cleaned_preprocessed_data.csv
```

## 📊 Key Insights

- **Total K-dramas analyzed:** 1,000+
- **Rating range:** 0–10 (IMDB)
- **Peak years:** Identify when most dramas aired
- **Top genres:** Action, Romance, Comedy, Drama
- **Correlation:** Rating vs. votes, runtime, year

## 🔧 Dependencies

```
pandas>=1.3.0
numpy>=1.20.0
scikit-learn>=0.24.0
scipy>=1.7.0
matplotlib>=3.4.0
seaborn>=0.11.0
missingno>=0.5.0
jupyter>=1.0.0
```

Install all with:
```bash
pip install -r requirements.txt
```

## 📈 Output Files

| File | Description |
|------|-------------|
| `cleaned_preprocessed_data.csv` | Final cleaned dataset (ready for ML models) |
| `test.ipynb` | Notebook with all analysis & visualizations |

## 🐛 Troubleshooting

**Error: `NameError: name 'df_filled' not defined`**
- Run all cells in order using **Run All** button
- Or manually run each cell from top to bottom with Shift+Enter

**Error: `ModuleNotFoundError: No module named 'missingno'`**
```bash
pip install missingno
```

**Error: `votes` column not numeric**
- The preprocessing handles string votes (e.g., "1.5K", "2M")
- See `parse_votes()` function in visualization cell

## 📚 Next Steps

1. Build predictive models (regression, classification)
2. Sentiment analysis on synopses
3. Recommendation system based on genres/ratings
4. Time-series forecasting for future drama popularity

## 📄 License

Dataset: [Kaggle License](https://www.kaggle.com/datasets/zeynepesennur/the-ultimate-korean-drama-dataset-19692025?resource=download)

## 👤 Author

Created as a learning project for ML/AI data preprocessing techniques.

---

**Last Updated:** December 16, 2025