# F1 Predictor 2025

A comprehensive Formula 1 race prediction system that uses machine learning, news sentiment analysis, and betting odds to predict podium probabilities for upcoming races.

## Features

- **Machine Learning Model**: Uses stacked ensemble of XGBoost, LightGBM, and CatBoost models to predict podium probabilities
- **News Sentiment Analysis**: Incorporates sentiment from F1 news articles to adjust predictions
- **Betting Odds Integration**: Compares model predictions with market odds from major bookmakers
- **Dynamic Schedule Parser**: Automatically fetches and updates the F1 race calendar
- **Visualization Dashboard**: Creates comprehensive visualizations of predictions and comparisons
- **Automated Pipeline**: End-to-end automation of data collection, feature engineering, model training, and visualization

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/f1-predictor-2025.git
cd f1-predictor-2025
```

2. Create a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Set up API keys (optional):
```bash
# For betting odds API
export ODDS_API_KEY="your_api_key_here"
```

## Usage

### Running the Full Pipeline

To run the complete pipeline with all features:

```bash
python src/master_pipeline.py --update-schedule --include-news --include-betting --create-visualizations
```

### Command Line Arguments

- `--update-schedule`: Update the race schedule before running the pipeline
- `--include-news`: Include news sentiment analysis in the pipeline
- `--include-betting`: Include betting odds analysis in the pipeline
- `--create-visualizations`: Create visualizations after running the pipeline

### Running Individual Components

You can also run individual components of the pipeline:

```bash
# Update race schedule
python src/schedule_parser.py

# Analyze news sentiment
python src/news_analyzer.py

# Fetch betting odds
python src/betting_odds_analyzer.py

# Engineer features
python src/feature_engineering.py

# Train model and make predictions
python src/model.py

# Create visualizations
python src/visualization.py
```

## Project Structure

```
f1-predictor-2025/
├── data/
│   ├── raw/              # Raw data files
│   └── processed/        # Processed data files
├── logs/                 # Pipeline logs
├── results/
│   └── visualizations/   # Generated visualizations
├── src/
│   ├── master_pipeline.py        # Main pipeline script
│   ├── schedule_parser.py        # Race schedule parser
│   ├── news_analyzer.py          # News sentiment analyzer
│   ├── betting_odds_analyzer.py  # Betting odds analyzer
│   ├── feature_engineering.py    # Feature engineering
│   ├── model.py                  # Model training and prediction
│   └── visualization.py          # Visualization generator
├── notebooks/            # Jupyter notebooks for analysis
├── requirements.txt      # Project dependencies
└── README.md            # Project documentation
```

## Model Details

The prediction model uses a stacked ensemble approach:

1. **Base Models**:
   - XGBoost
   - LightGBM
   - CatBoost

2. **Features**:
   - Historical performance
   - Recent form
   - Grid position
   - Circuit characteristics
   - News sentiment (optional)
   - Betting odds (optional)

3. **Output**:
   - Podium probability for each driver in upcoming races

## Visualization Dashboard

The visualization dashboard includes:

1. **Podium Probabilities**: Bar charts showing the probability of each driver finishing on the podium
2. **Probability Comparison**: Side-by-side comparison of model predictions and betting odds
3. **Race Calendar**: Overview of top 3 predicted drivers for each race in the season

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Formula 1 for race data
- Various F1 news websites for content
- Bookmakers for odds data
- The open-source community for machine learning libraries
