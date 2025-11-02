# Stock Analysis & Forecasting with ARIMA

A comprehensive Python-based stock market analysis tool that performs risk-return analysis, time series forecasting using ARIMA models, and provides personalized investment recommendations based on user risk profiles.

## Features

- **Portfolio Metrics Analysis**: Calculate annualized returns, volatility, and Sharpe ratios for multiple stocks
- **Statistical Analysis**: Correlation analysis and distribution visualization of key metrics
- **Outlier Detection & Treatment**: IQR-based outlier capping for robust analysis
- **Time Series Forecasting**: ARIMA (5,1,0) model for stock price prediction
- **Model Evaluation**: Mean Absolute Percentage Error (MAPE) calculation
- **Interactive Forecasting**: User-driven analysis with customizable date ranges
- **Risk-Based Recommendations**: Personalized buy/hold/sell suggestions based on risk tolerance
- **User Feedback Collection**: Built-in system to gather prediction accuracy ratings

## Installation

1. Clone the repository:
```bash
git clone https://github.com/AnjaliiD/stock-analysis-arima-forecasting.git
cd stock-analysis-arima-forecasting
```

2. Install required dependencies:
```bash
pip install -r requirements.txt
```

3. Prepare your data:
   - Ensure you have a CSV file named `top_50_stocks_data_formatted.csv` with columns:
     - `Ticker`: Stock symbol
     - `Date`: Trading date
     - `Open`, `High`, `Low`, `Close`: Price data
     - `Adjusted Close`: Adjusted closing price
     - `Volume`: Trading volume

## Usage

Run the main analysis script:

```bash
jupyter notebook stock_analysis.ipynb
```

### Interactive Inputs

The program will prompt you for:

1. **Company Tickers**: Enter stock symbols separated by commas (e.g., `AAPL,GOOGL,MSFT`)
2. **Start Date**: Analysis start date in `YYYY-MM-DD` format
3. **End Date**: Analysis end date in `YYYY-MM-DD` format
4. **Prediction Ratings**: Rate the accuracy of predictions (1-5 scale)
5. **Improvement Suggestions**: Provide feedback for model enhancement
6. **Risk Level**: Your risk tolerance (`low`, `medium`, or `high`)

### Example

```
Enter the company's abbreviated names separated by commas: AAPL,GOOGL
Enter the start date YYYY-MM-DD: 2023-01-01
Enter the end date YYYY-MM-DD: 2024-01-01
After Use Please rate the accuracy of the prediction for AAPL (1-5): 4
Please provide any suggestions for improving the prediction for AAPL: Consider seasonal trends
Enter your risk level (low, medium, high): medium
```

## Output

The tool generates:

1. **Distribution Plots**: Histograms with KDE for return, volatility, and Sharpe ratio
2. **Correlation Heatmap**: Relationships between portfolio metrics
3. **Price Prediction Charts**: Original vs. predicted vs. forecasted prices
4. **MAPE Scores**: Model accuracy metrics for each stock
5. **10-Day Forecasts**: Future price predictions
6. **Investment Recommendations**: Personalized based on volatility and risk profile

## Risk Thresholds

- **Low Risk**: Volatility < 0.2 (20%)
- **Medium Risk**: Volatility < 0.5 (50%)
- **High Risk**: Volatility < 1.0 (100%)

## Model Details

- **ARIMA Configuration**: (5,1,0) - 5 autoregressive terms, 1st order differencing
- **Risk-Free Rate**: 1% (adjustable in code)
- **Forecast Horizon**: 10 trading days
- **Outlier Treatment**: IQR method with 1.5x multiplier

## File Structure

```
stock-analysis-arima-forecasting/
│
├── stock_analysis.py              # Main analysis script
├── requirements.txt                # Python dependencies
├── README.md                       # Documentation
└── top_50_stocks_data_formatted.csv  # Input data (user-provided or given in repository)
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## Acknowledgments

- Data sourced using `yfinance` library
- ARIMA implementation via `statsmodels`
- Visualization powered by `matplotlib` and `seaborn`

## Disclaimer

This tool is for educational and research purposes only. It should not be considered financial advice. Always consult with a qualified financial advisor before making investment decisions. Past performance does not guarantee future results.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For questions or suggestions, please open an issue on GitHub or email me at anjalidesai0111@gmail.com.

**Note**: Ensure your dataset covers sufficient historical data (at least 1-2 years) for reliable ARIMA modeling and forecasting.
